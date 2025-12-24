<!DOCTYPE html>
<html>
<head>
    <title>Study Planner</title>
    <style>
        body {
            font-family: Arial;
            background-color: #eef2f7;
            text-align: center;
            padding-top: 30px;
        }
        h1 {
            color: #2c3e50;
        }
        input, select {
            padding: 8px;
            margin: 5px;
        }
        button {
            padding: 8px 15px;
            background-color: #6c5ce7;
            color: white;
            border: none;
            cursor: pointer;
        }
        table {
            margin: auto;
            margin-top: 20px;
            border-collapse: collapse;
            width: 70%;
            background: white;
        }
        th, td {
            border: 1px solid #ccc;
            padding: 10px;
        }
        th {
            background-color: #dfe6e9;
        }
    </style>
</head>

<body>

    <h1>Study Planner</h1>

    <input type="text" id="subject" placeholder="Subject name">
    <select id="day">
        <option>Saturday</option>
        <option>Sunday</option>
        <option>Monday</option>
        <option>Tuesday</option>
        <option>Wednesday</option>
        <option>Thursday</option>
    </select>
    <input type="time" id="time">
    <button onclick="addPlan()">Add</button>

    <table>
        <tr>
            <th>Subject</th>
            <th>Day</th>
            <th>Time</th>
        </tr>
        <tbody id="planner"></tbody>
    </table>

    <script>
        function addPlan() {
            var subject = document.getElementById("subject").value;
            var day = document.getElementById("day").value;
            var time = document.getElementById("time").value;

            if(subject !== "" && time !== ""){
                var row = document.createElement("tr");

                row.innerHTML =
                    "<td>" + subject + "</td>" +
                    "<td>" + day + "</td>" +
                    "<td>" + time + "</td>";

                document.getElementById("planner").appendChild(row);

                document.getElementById("subject").value = "";
                document.getElementById("time").value = "";
            }
        }
    </script>

</body>
</html>
