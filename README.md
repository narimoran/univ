<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>University Planner(2024/2025)</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #e69a9a;
            color: black;
            margin: 0;
            padding-top: 120px;
        }
        h1 {
            position: fixed;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            background-color: #f2f2f2;
            padding: 15px 30px;
            border-radius: 25px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            margin: 0;
            text-align: center;
            z-index: 1000;
            animation: floatTitle 3s infinite alternate ease-in-out;
        }
        @keyframes floatTitle {
            0% {
                transform: translateX(-50%) translateY(0);
            }
            100% {
                transform: translateX(-50%) translateY(10px);
            }
        }
        table {
            width: 80%;
            margin: 80px auto 0 auto;
            border-collapse: collapse;
            background-color: #c3c9f7;
            color: black;
        }
        th, td {
            border: 1px solid black;
            padding: 10px;
            text-align: center;
            background-color: #c3c9f7;
            color: black;
        }
        th {
            background-color: #f2f2f2;
        }
        input {
            width: 90%;
            padding: 5px;
        }
        button {
            margin-top: 20px;
            padding: 10px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>University Weekly Planner</h1>
    <table>
        <tr>
            <th>Time</th>
            <th>Sunday</th>
            <th>Monday</th>
            <th>Tuesday</th>
            <th>Wednesday</th>
            <th>Thursday</th>
        </tr>
        <tr>
            <td>08:30 - 10:00</td>
            <td>Cours Thermodynamique</td>
            <td>Cours Méthode Numérique</td>
            <td>TD Solution</td>
            <td>TP Solution et Organique</td>
            <td>Cours Organique</td>
        </tr>
        <tr>
            <td>10:00 - 11:30</td>
            <td>Cours Cinétique</td>
            <td>TD Méthode Numérique</td>
            <td>TD Organique</td>
            <td>TP Cinétique</td>
            <td>Cours Solution</td>
        </tr>
        <tr>
            <td>11:45 - 13:15</td>
            <td>TP MDF</td>
            <td></td>
            <td>TD Thermodynamique</td>
            <td>TP Méthode Numérique</td>
            <td>Cours Raffinage</td>
        </tr>
        <tr>
            <td>13:50 - 14:45</td>
            <td>tp mdf</td>
            <td>cours tech et cmnc</td>
            <td></td>
            <td>tp</td>
            <td>Cours Phénomène</td>
        </tr>
    </table>
    <button onclick="downloadPDF()">Download as PDF</button>
    
    <script>
        function downloadPDF() {
            const { jsPDF } = window.jspdf;
            const doc = new jsPDF();
            doc.text("University Weekly Planner", 10, 10);
            
            let y = 20;
            const table = document.querySelector("table");
            for (let row of table.rows) {
                let x = 10;
                for (let cell of row.cells) {
                    const text = cell.innerText;
                    doc.text(text, x, y);
                    x += 35;
                }
                y += 10;
            }
            
            doc.save("university_planner.pdf");
        }
    </script>
</body>
</html>
