# CSS-JavaScript Code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Event Object Example</title>
    <!-- <link rel="stylesheet" href="style.css"> -->
    <!-- https://mycolor.space/gradient?ori=to+top&hex=%23E33FCE&hex2=%2391AC56&sub=1 -->
     <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        html {
            font-size: 1rem;
            color: #fff;
            box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.1);
        }
        h2 {
            margin-top: 1rem;
            box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.1);
        }
        body {
            width: 100%;
            height: 100vh;
            background-image: linear-gradient(
                to right top,
                #051937,
                #004d7a,
                #008793,
                #00bf72,
                #a8eb12
            );
            display: flex;
            justify-content: center;
            align-items: center;
        }
        section {
            padding: 2rem;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }
        #myButton {
            /* background-color: rgb(168, 235, 18);
            color: rgb(34, 34, 34); */
            background: linear-gradient(to right, #000, #000);
            color: #fff;
            border: none;
            padding: 0.8rem 1.5rem;
            margin: 0 0.5rem;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.4s, transform 0.3s;
            
        }
        #myButton2 {
            /* background-color: rgb(168, 235, 18);
            color: rgb(34, 34, 34); */
            /* box-shadow: 10px 10px 1px rgba(00, 00, 00, 0.2); */
            background: linear-gradient(to right, #000, #000);
            color: #fff;
            border: none;
            padding: 0.8rem 1.5rem;
            margin: 0 0.5rem;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.4s, transform 0.3s;
        }
        .copyCode {
            color: white;
            font-family: 'Times New Roman', Times, serif;
            padding: 1rem 2rem;
            border-radius: 10px;
            box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.1);
            max-width: 500px;
            text-align: center;
            word-break: break-word;
        }

/* button:hover {
    background: linear-gradient(to right, #008793, #051937);
    transform: scale(1.05);
} */
     </style>
</head>
<body>
    <section>
        <div>
            <button id="myButton">#051937</button>
            <button id="myButton2">#008793</button>
        </div>
        <h2>Copy Your Code Here On Right Click</h2>
        <div class="copyCode">
            background-image: linear-gradient(to right, rgb(92, 145, 229), rgb(152, 63, 198))
        </div>
    </section>
    <script>
        let btn1 = document.getElementById("myButton");
        let btn2 = document.getElementById("myButton2");
        let copyDiv = document.querySelector(".copyCode");
        let rgb1 = "#004773";
        let rgb2 = "#54d542";
        // todo to get the default color we can add the actual color here

        const hexValues = () => {
            let myHexValues = "0123456789abcdef";
            let colors = "#";
            for (let i = 0; i < 6; i++) {
                colors = colors + myHexValues[Math.floor(Math.random() * 16)];  
            }
            return colors;
        };

        const handleButton1 = () => {
          rgb1 = hexValues();
          console.log(rgb1);
          btn1.innerText = rgb1;
          document.body.style.backgroundImage = `linear-gradient(to right, ${rgb1}, ${rgb2})`;
          copyDiv.innerHTML = `background-image: liner-gradient(to right, ${rgb1}, ${rgb2})`;
        };

        const handleButton2 = () => {
          rgb2 = hexValues();
          console.log(rgb2);
          btn2.innerText = rgb2;
          document.body.style.backgroundImage = `linear-gradient(to right, ${rgb1}, ${rgb2})`;
          copyDiv.innerHTML = `background-image: liner-gradient(to right, ${rgb1}, ${rgb2})`;
        };
        
        btn1.addEventListener("click", handleButton1);
        btn2.addEventListener("click", handleButton2);

        copyDiv.addEventListener("click", () => {
            navigator.clipboard.writeText(copyDiv.innerText);
            alert("Copy Code ")
        });
        
    </script>
</body>
</html>
