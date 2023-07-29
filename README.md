# PinnetiMaheswari
te.html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <title>Text Editor</title>
    <style>
      #editor {
        width: 100%;
        height: 300px;
        border: 1px solid black;
      }
    </style>
  </head>
  <body>
    <h1>Text Editor</h1>
    <textarea id="editor"></textarea>
    <button onclick="save()">Save</button>
    <script src="TE.js"></script>
  </body>
</html>

te.css
#editor {
  width: 100%;
  height: 300px;
  border: 1px solid black;
}

te.js
const editor = document.getElementById('editor');

function save() {
  const text = editor.value;
  const filename = prompt('Enter a filename:', 'Untitled.txt');
  const element = document.createElement('a');
  element.setAttribute('href', 'data:text/plain;charset=utf-8,' + encodeURIComponent(text));
  element.setAttribute('download', filename);
  element.style.display = 'none';
  document.body.appendChild(element);
  element.click();
  document.body.removeChild(element);
}
