<!DOCTYPE html>
<html>
<head>
	<title>Carbon Footprint Calculator</title>
	<style>
		form {
			display: flex;
			flex-direction: column;
			align-items: center;
		}

		label {
			margin-top: 10px;
			margin-bottom: 5px;
			font-weight: bold;
		}

		input[type="number"] {
			width: 100px;
			margin-left: 10px;
		}

		input[type="submit"] {
			margin-top: 20px;
			padding: 10px;
			background-color: #4CAF50;
			color: white;
			border: none;
			border-radius: 5px;
			cursor: pointer;
		}

		input[type="submit"]:hover {
			background-color: #3e8e41;
		}
	</style>
</head>
<body>
	<h2>Carbon Footprint Calculator</h2>
	<form>
		<label for="electricity">Electricity (kWh):</label>
		<input type="number" id="electricity" name="electricity"><br>
		<label for="gas">Gas (therms):</label>
		<input type="number" id="gas" name="gas"><br>
		<label for="oil">Oil (gallons):</label>
		<input type="number" id="oil" name="oil"><br>
		<label for="propane">Propane (gallons):</label>
		<input type="number" id="propane" name="propane"><br>
		<label for="flight">Flight (miles):</label>
		<input type="number" id="flight" name="flight"><br>
		<label for="car">Car (miles):</label>
		<input type="number" id="car" name="car"><br>
		<input type="submit" value="Calculate">
	</form>
	<script>
		document.querySelector("form").addEventListener("submit", function(event) {
			event.preventDefault();
			var electricity = document.getElementById("electricity").value;
			var gas = document.getElementById("gas").value;
			var oil = document.getElementById("oil").value;
			var propane = document.getElementById("propane").value;
			var flight = document.getElementById("flight").value;
			var car = document.getElementById("car").value;
			var total = (electricity * 0.0006) + (gas * 11.7) + (oil * 22.4) + (propane * 12.7) + (flight * 0.00028) + (car * 0.0004);
			alert("Your carbon footprint is " + total.toFixed(2) + " metric tons of CO2 per year.");
		});
	</script>
</body>
</html>
