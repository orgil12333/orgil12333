<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Checklist with Sound</title>
<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f0f0f0;
        margin: 0;
        padding: 0;
    }
    h1 {
        text-align: center;
        margin-top: 20px;
    }
    .container {
        max-width: 600px;
        margin: 20px auto;
        background-color: #fff;
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }
    .challenge {
        margin-bottom: 10px;
    }
    .challenge label {
        display: block;
        padding-left: 30px;
        position: relative;
        cursor: pointer;
        font-size: 16px;
    }
    .challenge input[type="checkbox"] {
        position: absolute;
        left: 0;
        top: 50%;
        transform: translateY(-50%);
    }
    .challenge input[type="checkbox"] + label:before {
        content: '';
        display: inline-block;
        width: 20px;
        height: 20px;
        border: 1px solid #ccc;
        border-radius: 4px;
        position: absolute;
        left: 0;
        top: 50%;
        transform: translateY(-50%);
    }
    .challenge input[type="checkbox"]:checked + label:before {
        background-color: #4CAF50;
        border-color: #4CAF50;
    }
    .challenge input[type="checkbox"]:checked + label:after {
        content: '\2713';
        font-size: 14px;
        color: #fff;
        position: absolute;
        left: 5px;
        top: 2px;
    }
</style>
</head>
<body>

<h1>Checklist with Sound</h1>

<div class="container">
    <div class="challenge">
        <input type="checkbox" id="task1" onclick="checkCompletion()">
        <label for="task1">Task 1: Example task 1</label>
    </div>

    <div class="challenge">
        <input type="checkbox" id="task2" onclick="checkCompletion()">
        <label for="task2">Task 2: Example task 2</label>
    </div>

    <!-- Add more tasks as needed -->

</div>

<audio id="congrats-sound" src="https://pixabay.com/sound-effects/new-notification-7-210334/"></audio>

<script>
    function checkCompletion() {
        const checkboxes = document.querySelectorAll('.challenge input[type="checkbox"]');
        const allChecked = Array.from(checkboxes).every(checkbox => checkbox.checked);

        if (allChecked) {
            document.getElementById('congrats-sound').play();
        }
    }
</script>

</body>
</html>
