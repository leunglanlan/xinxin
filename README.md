[my_heart_for_you.html](https://github.com/user-attachments/files/22019174/my_heart_for_you.html)
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>我有一颗心，想要请你收下</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background: url('你的背景图链接.jpg') no-repeat center center fixed; /* 可选：改成你的图片路径 */
            background-size: cover;
            color: #333;
            padding: 50px;
        }
        .container {
            background-color: rgba(255, 255, 255, 0.9);
            max-width: 600px;
            margin: 0 auto;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 0 20px rgba(255, 105, 180, 0.5);
        }
        h1 { color: #ff69b4; } /* 粉红色 */
        code {
            background-color: #f8f8f8;
            padding: 15px;
            border-radius: 5px;
            display: block;
            text-align: left;
            margin: 20px 0;
            font-size: 16px;
            border-left: 4px solid #ff69b4;
        }
        input, button {
            padding: 10px 15px;
            margin: 10px;
            border: none;
            border-radius: 5px;
            font-size: 16px;
        }
        input {
            border: 1px solid #ccc;
            width: 200px;
        }
        button {
            background-color: #ff69b4;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        button:hover {
            background-color: #ff1493;
        }
        #result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
            color: #ff69b4;
            min-height: 50px;
        }
        .heart {
            color: red;
            font-size: 24px;
            animation: pulse 1.5s infinite;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.3); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- 第一步：展示代码 -->
        <h1>💗 我的心就是一个数据库 💗</h1>
        <p>我写了一段最特别的代码，只想为你运行。</p>
        <code>CREATE TABLE my_heart (<br>
        &nbsp;&nbsp;your_name VARCHAR(50) PRIMARY KEY,<br>
        &nbsp;&nbsp;love_degree INT DEFAULT 999999,<br>
        &nbsp;&nbsp;forever_flag BOOLEAN DEFAULT TRUE<br>
        );</code>
        <p>它的意思是：<br>我的心里永远为你保留了一个<strong>唯一</strong>的位置，<br>这份爱的默认值是<strong>无限大</strong>，并且默认状态是<strong>永恒</strong>。</p>

        <hr>

        <!-- 第二步：互动 -->
        <h2>你愿意成为这条记录吗？</h2>
        <p>请输入你的名字，然后点击执行：</p>
        <input type="text" id="nameInput" placeholder="请输入你的名字">
        <button onclick="runSQL()">执 行 ↗</button>
        <div id="result"></div>
    </div>

    <script>
        function runSQL() {
            const name = document.getElementById('nameInput').value.trim();
            if (!name) {
                alert("请输入你的名字！");
                return;
            }

            // 这里是“模拟”数据库操作，但效果很浪漫
            const resultDiv = document.getElementById('result');
            
            // 模拟“插入”和“查询”的过程，添加一点延迟增加仪式感
            resultDiv.innerHTML = "> 正在连接到 My_Heart 数据库...<br>";
            
            setTimeout(() => {
                resultDiv.innerHTML += "> 正在创建专属记录...<br>";
            }, 800);
            
            setTimeout(() => {
                resultDiv.innerHTML += `> INSERT INTO my_heart (your_name) VALUES ('${name}');<br>`;
                resultDiv.innerHTML += "<span class='heart'>♥</span> 记录成功！<br>";
            }, 1600);
            
            setTimeout(() => {
                resultDiv.innerHTML += "> SELECT * FROM my_heart WHERE your_name = '" + name + "';<br>";
            }, 2400);
            
            setTimeout(() => {
                // 最终显示查询结果
                resultDiv.innerHTML += `
                <br>
                <strong>查询结果：</strong><br>
                =========================<br>
                | your_name  | ${name} |<br>
                | love_degree | <span style="color: red;">999999</span>  |<br>
                | forever_flag | <span style="color: red;">TRUE</span>   |<br>
                =========================<br>
                <br>
                <h2>恭喜你！你已经成为我心中最重要、唯一的数据。</h2>
                <p>我的心（数据库）将永远为你运行。</p>
                `;
            }, 3200);
        }
    </script>
</body>
</html>
