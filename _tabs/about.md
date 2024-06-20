---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---
<html>
<head>
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
<script language="javascript">
function getOPR() {
    axios.get("https://api.ftcscout.org/rest/v1/teams/15031/quick-stats?season=2023&region=All")
        .then(response => {
            var opr = response.data["tot"]["value"];
            document.getElementById("opr").innerHTML = opr;
    }) 
rl.close();
}</script>
</head>

<body onload = "getOPR()">
<p>Hello!</p>

<p>I'm Iris! I'm trans, 16, and enjoy programing and playing games. Im a member of First Tech Challange 15031, BoltBusterZ.</p>

<p>My particular interests include combat robotics, Valorant Esports, and finding new ways to procrastinate doing my homework<p>

<p> BoltBusterZ OPR is currently: <b><span id = "opr"></span></b></p>