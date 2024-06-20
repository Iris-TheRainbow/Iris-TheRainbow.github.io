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
            var rank = Math.min(response.data["auto"]["rank"], response.data["dc"]["rank"], response.data["eg"]["rank"]);
            var value = "";
            var best = "";
            if (rank == response.data["auto"]["rank"]){
                best = "autonomus";
                value = response.data["auto"]["value"];
            } else if (rank == response.data["dc"]["rank"]){
                best = "teleOp";
                value = response.data["dc"]["value"];
            } else if (rank == response.data["eg"]["rank"]){
                best = "endgame";
                value = response.data["eg"]["value"];
            }
            document.getElementById("opr").innerHTML = opr;
            document.getElementById("value").innerHTML = Math.round(value*100)/100;
            document.getElementById("best").innerHTML = best;
        });
    axios.get("https://vlr.orlandomm.net/api/v1/teams/2")
        .then(response => {
            var team0 = response.data.data.upcoming["0"]["teams"]["0"]["tag"];
            var team1 = response.data.data.upcoming["0"]["teams"]["1"]["tag"];
            document.getElementById("team0").innerHTML = team0;
            document.getElementById("team1").innerHTML = team1;            
        })};
</script>

</head>

<body onload = "getOPR()">
<p>Hello!</p>

<p>I'm Iris! I'm trans, 16, and enjoy programing and playing games. Im a member of First Tech Challange 15031, BoltBusterZ.</p>

<p>My particular interests include robotics, Valorant Esports, and finding new ways to procrastinate doing my homework<p>

<p> BoltBusterZ OPR is currently <b><span id = "opr"></span></b>. Our best OPR is <b><span id = "best"></span></b> with <b><span id = "value"></span></b>.</p>

<p> The next Sentinels match is <b><span id = "team0"></span> vs <span id = "team1"></span></b>, which <b>SEN</b> has a <b>100% </b> chance of winning. </p>