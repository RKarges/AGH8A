<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>AHN-8A</title>
	<script   src="https://code.jquery.com/jquery-3.5.1.min.js"   integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0="   crossorigin="anonymous"></script>
</head>
<style>
	body { 
		font-family: Sans-serif; 
		background-color: #eee;
	}

	table { 
		width: 100%;
	}

	thead tr
	{
		background-color: #275F5D;
		color: white;
	}
	th, td {
		padding: 5px 5px;
	}
	
	tbody tr:nth-child(even) {
		background-color: #ddd;
	}
	
	input {
		width: 50%;
		font-size: 20px;
		border-radius: 6px;
	}
	#clear { 
		font-size: 20px; 
		position: relative;
		top: -2px;
	}
	#search {
		padding-bottom: 10px;
	}
</style>
<body>
<h1>AHN-8A</h1>

<div id="search"><input type="text" placeholder="Search..." /><button id="clear"">Clear</div>

<table>
	<thead>
		<tr>
			<th id="department">Department</th>
			<th id="contact">Contact</th>
			<th id="number">Number</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>AGH Operator</td>
			<td>Main Number</td>
			<td><a href="tel://412-359-3131">412-359-3131</a></td>
		</tr>
		<tr>
			<td>Angio</td>
			<td>Main</td>
			<td><a href="tel://412-359-3755">412-359-3755</a></td>
		</tr>
		<tr>
			<td>Apothecary</td>
			<td>Main</td>
			<td><a href="tel://412-359-8677">412-359-8677</a></td>
		</tr>
	</tbody>
</table>

<script>
$(function() {
	$("input").on('input', function() {
		var needle = $("input").val().toLowerCase();
		$("tbody tr").hide(); // hide all, then show the matches
		$("tbody td").filter(function() {
			console.log("Text: "+ $(this).text().toLowerCase() + "; search: " + $(this).text().toLowerCase().indexOf(needle))
			return $(this).text().toLowerCase().indexOf(needle) !== -1;
		}).parent().show()
	})
	
	$("#clear").click(function() { 
		$("input").val("").focus();
		$("tbody tr").show();
	 })
})
</script>
</body>
</html>

