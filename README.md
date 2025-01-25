<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random No Button</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: whitesmoke;
        }

        .wrapper {
            position: relative;
            width: 100%;
            max-width: 400px;
            text-align: center;
        }

        h2 {
            font-size: 2em;
            color: #e94d58;
            margin: 15px 0;
        }

        .gif {
            width: 100%;
            max-width: 300px;
        }

        .btn-group {
            margin-top: 50px;
            position: relative;
            height: 40px;
        }

        button {
            width: 150px;
            height: inherit;
            color: white;
            font-size: 1.2em;
            border-radius: 30px;
            outline: none;
            cursor: pointer;
            box-shadow: 0 2px 4px gray;
            border: 2px solid #e94d58;
        }

        button.yes-btn {
            background: #e94d58;
        }

        button.no-btn {
            background: white;
            color: #e94d58;
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
        }
    </style>
</head>
<body>
    <div class="wrapper">
        <h2 class="question">Do You Love Me?</h2>
        <img class="gif" alt="gif" src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExOTlnamRuZHphOHE3b2preGtrbGVqZ3o0dTByNWpscXA2eG91ZDVreCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/CM1rHbKDMH2BW/giphy.gif" />
        <div class="btn-group">
            <button class="yes-btn">Yes</button>
            <button class="no-btn">No</button>
        </div>
    </div>
    <script>
        const yesBtn = document.querySelector(".yes-btn");
        const noBtn = document.querySelector(".no-btn");
        const question = document.querySelector(".question");
        const gif = document.querySelector(".gif");

        // Change text and gif when the Yes button is clicked
        yesBtn.addEventListener("click", () => {
          question.innerHTML = "I love You To!!";
  gif.src = "https://media.giphy.com/media/PqLcW0s1xWz0ySP6Ed/giphy.gif?cid=790b7611iqv96qigofgcfck1v4ijgqs3wsuqmp5v4w7goudj&ep=v1_gifs_search&rid=giphy.gif&ct=g";
        });

        // Make the No button move randomly on hover
        noBtn.addEventListener("mouseover", () => {
          const wrapper = document.querySelector(".wrapper");
          const wrapperRect = wrapper.getBoundingClientRect();
          const noBtnRect = noBtn.getBoundingClientRect();

          // Calculate max positions to ensure the button stays within the wrapper
          const maxX = wrapperRect.width - noBtnRect.width;
          const maxY = wrapperRect.height - noBtnRect.height;

          const randomX = Math.floor(Math.random() * maxX);
          const randomY = Math.floor(Math.random() * maxY);

          noBtn.style.left = randomX + "px";
          noBtn.style.top = randomY + "px";
        });
    </script>
</body>
</html>
