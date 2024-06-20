---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---
<script language = 'javascript'> 
function getOPR()
    axios.get("https://api.ftcscout.org/rest/v1/teams/15031/quick-stats?season=2023&region=All")
        .then(response => {
            return response.data["tot"]["value"];
        })
        rl.close();
</script>
Hello!

I'm Iris! I'm trans, 16, and enjoy programing and playing games. Im a member of First Tech Challange 15031, BoltBusterZ. 

My particular interests include combat robotics, Valorant Esports, and finding new ways to procrastinate doing my homework.

<p>BoltBusterZ OPR is currently: <b><script>getOPR()</script></b></p>