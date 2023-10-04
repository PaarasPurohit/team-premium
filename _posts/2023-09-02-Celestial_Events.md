---
toc: true
comments: true
layout: post
title: Test Celestial API
description: xx
permalink: /celestialAPI
type: hacks
courses: { compsci: {week: 7} }
---

<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Celestial Data Display</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            background-color: black;
            color: cyan;
        }

        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
            background: linear-gradient(to right, #000, #000);
        }

        th, td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid cyan;
        }

        th {
            background-color: #111;
            font-weight: bold;
        }

        tr:hover {
            background-color: #111;
        }
    </style>
</head>
<body>
    <h1>Celestial Data</h1>
    <table>
        <thead>
            <tr>
                <th>Name</th>
                <th>Date</th>
                <th>Distance (km)</th>
                <th>Distance (AU)</th>
                <th>Magnitude</th>
                <th>Altitude (degrees)</th>
                <th>Azimuth (degrees)</th>
                <th>Constellation</th>
                <th>Right Ascension</th>
                <th>Declination</th>
            </tr>
        </thead>
        <tbody id="table-body"></tbody>
    </table>
<script>
  async function makeRequest() {
    const url = 'https://astronomy.p.rapidapi.com/api/v2/bodies/positions?latitude=33.775867&longitude=-84.39733&from_date=2017-12-20&to_date=2017-12-21&elevation=166&time=12%3A00%3A00';
    const options = {
      method: 'GET',
      headers: {
        'X-RapidAPI-Key': '8401db6433msh3a46dd5bf23ad2ep19a280jsn48536a994246',
        'X-RapidAPI-Host': 'astronomy.p.rapidapi.com'
      }
    };
    try {
      const response = await fetch(url, options);
      const data = await response.json();

      const tableBody = document.getElementById('table-body');
      data.data.table.rows.forEach(row => {
        const cell = row.cells[0]; // We'll just use the first cell for simplicity
        const position = cell.position.horizontal;

        const newRow = tableBody.insertRow();
        newRow.insertCell(0).innerText = cell.name;
        newRow.insertCell(1).innerText = cell.date;
        newRow.insertCell(2).innerText = cell.distance.fromEarth.km;
        newRow.insertCell(3).innerText = cell.distance.fromEarth.au;
        newRow.insertCell(4).innerText = cell.extraInfo.magnitude;
        newRow.insertCell(5).innerText = position.altitude.degrees;
        newRow.insertCell(6).innerText = position.azimuth.degrees;
        newRow.insertCell(7).innerText = cell.position.constellation.name;
        newRow.insertCell(8).innerText = cell.position.equatorial.rightAscension.string;
        newRow.insertCell(9).innerText = cell.position.equatorial.declination.string;
      });
    } catch (error) {
      console.error(error);
    }
  }

  // Call the function to make the request and display the data in the table
  makeRequest();
</script>
</body>
</html>