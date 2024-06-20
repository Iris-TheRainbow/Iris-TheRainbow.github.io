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
            var opr = Math.round((response.data["tot"]["value"])*100)/100;
            document.getElementById("opr").innerHTML = opr;
            var rank = Math.min(response.data["auto"]["rank"], response.data["dc"]["rank"], response.data["eg"]["rank"]);
            var value = Math.min(response.data["auto"]["value"], response.data["dc"]["value"], response.data["eg"]["value"]);
            console.log(value)
            document.getElementById("value").innerHTML = Math.round(value*100)/100;
            if (rank == response.data["auto"]["rank"]){
                var best = "autonomus";
            } else if (rank == response.data["dc"]["rank"]){
                var best = "teleOp";
            } else if (rank == response.data["eg"]["rank"]){
                var best = "endgame";
            }
            document.getElementById("best").innerHTML = best;
        })};
</script>
</head>

<body onload = "getOPR()">
<p>Hello!</p>

<p>I'm Iris! I'm trans, 16, and enjoy programing and playing games. Im a member of First Tech Challange 15031, BoltBusterZ.</p>

<p>My particular interests include combat robotics, Valorant Esports, and finding new ways to procrastinate doing my homework<p>

<p> BoltBusterZ OPR is currently <b><span id = "opr"></span></b>. Our best OPR is <b><span id = "best"></span></b> with <b><span id = "value"></span></b>.</p>