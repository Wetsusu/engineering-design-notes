# DOMオーバーレイを使用したiframe操作

## 実装パターン

リファレンスが限定的な独自フレームワークでのDOMとiframe間の複雑な連動処理を実装したパターンです。

### 概要

リファレンスが限定的な独自フレームワーク上で、透明なDOMオーバーレイを使用してiframe内のエディタを操作・同期する実装パターン。

## コード実装

```javascript
// 1. iframe内オブジェクト参照取得（事前準備）

const iframe = document.getElementById('editor-iframe');

const editorObj = iframe.contentWindow.EditorInstance;  // 独自フレームワークがグローバルに露出している前提

// 2. 検証プロセス（実際に行ったリバースエンジニアリング）

function inspectProperties(obj) {

  for (let prop in obj) {

    if (typeof obj[prop] === 'function' || typeof obj[prop] === 'number') {

      console.log(prop, obj[prop]);

      // 値を少し変えて描画変化を観察 → スクロール制御プロパティ特定

      // 例: obj.someScrollProp = newValue → iframeスクロール変化を確認

    }

  }

}

// → 結果、editorObj.scrollTop, editorObj.lineHeight, editorObj.clickAtLine(line, offset) などを特定

// 3. スクロール同期

overlay.addEventListener('scroll', debounce(() => {

  const scrollTop = overlay.scrollTop;

  const scrollLeft = overlay.scrollLeft;

  editorObj.setScrollPosition(scrollTop, scrollLeft);  // 特定したプロパティ/メソッドで反映

}, 10));

// 4. 行高さ同期 + 透明行生成

function syncLineHeights() {

  const lineHeight = editorObj.getLineHeight();  // 特定したメソッドで1行の高さ取得

  const lineCount = editorObj.getLineCount();

  overlay.innerHTML = '';  // クリア

  for (let i = 0; i < lineCount; i++) {

    const div = document.createElement('div');

    div.style.height = `${lineHeight}px`;

    div.style.opacity = '0';

    div.style.pointerEvents = 'none';  // 透過してクリックはiframeに届ける

    overlay.appendChild(div);

  }

}

syncLineHeights();  // 初期化 + 必要時再実行

// 5. クリックイベント再現

overlay.addEventListener('click', (e) => {

  const rect = overlay.getBoundingClientRect();

  const y = e.clientY - rect.top;

  const lineIndex = Math.floor(y / editorObj.getLineHeight());

  

  // iframe内にイベント転送（特定したメソッド使用）

  editorObj.focusLine(lineIndex);

  editorObj.simulateClick(lineIndex, 0);  // 実際の座標計算を追加

});  

```

## キーポイント

- **リバースエンジニアリング**: フレームワークのプロパティをコンソール出力と画面描画の変化で検証
- **DOMオーバーレイ**: 実際のコンテンツは透明で、イベント受信のみを行う
- **スクロール・行高さ同期**: iframe内の状態をオーバーレイと常に同期
- **イベント転送**: iframe内への適切なメソッド呼び出しでユーザー操作を再現
