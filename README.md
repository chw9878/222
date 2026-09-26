<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>영어 → 이진법 변환기</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 700px;
      margin: 50px auto;
      padding: 20px;
      background: #f4f4f4;
    }

    h1 {
      text-align: center;
    }

    textarea {
      width: 100%;
      height: 120px;
      padding: 10px;
      font-size: 16px;
      box-sizing: border-box;
      resize: vertical;
    }

    button {
      width: 100%;
      margin-top: 10px;
      padding: 12px;
      font-size: 16px;
      cursor: pointer;
      background: #222;
      color: white;
      border: none;
      border-radius: 5px;
    }

    button:hover {
      background: #444;
    }

    #result {
      margin-top: 20px;
      padding: 15px;
      min-height: 80px;
      background: white;
      border-radius: 5px;
      word-break: break-all;
      font-family: monospace;
      line-height: 1.8;
    }
  </style>
</head>

<body>

  <h1>영어 → 이진법 변환기</h1>

  <textarea id="input" placeholder="영어 문장을 입력하세요."></textarea>

  <button onclick="convertToBinary()">이진법으로 변환</button>

  <div id="result">여기에 결과가 표시됩니다.</div>

  <script>
    function convertToBinary() {
      const text = document.getElementById("input").value;

      const binary = [...text]
        .map(char => {
          const code = char.charCodeAt(0);
          return code.toString(2).padStart(8, "0");
        })
        .join(" ");

      document.getElementById("result").textContent =
        binary || "문장을 입력해주세요.";
    }
  </script>

</body>
</html>
