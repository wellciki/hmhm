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
        <h2 class="question">Do You Like Kentut?</h2>
        <img class="gif" alt="gif" src="https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExbjJvdWZzYXc1NGJ6aGp1cDE3b2dyNnVzOGN1andkMjVrMmRzeGwwZSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/3OhXBaoR1tVPW/giphy.gif" />
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
          question.innerHTML = "You got Rickrolled 😘 (FOLLOW ME @kristel_tech or 7 years bad luck)";
          gif.src = "https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExZGI1cW5wMWhpaDF5b3pjdTF0OHZrcHJvaGkzOHJteDhmd245OGRnZyZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/Vuw9m5wXviFIQ/giphy.gif";
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
