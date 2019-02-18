<template>
    <div id="contact" class="section">
        <div class="title">
            CONTACT
        </div>
        <div class="team">
          <div class="team-member">
            <img alt="Vue logo" src="../assets/aboutmePic.jpg" class="picture">
            <div class="resume">
              <p>
                Hi,
                <br/>
                <br/>
                My name is Cécile HUI BON HOA, I am a fullstack developer.
              </p>
              <p>
                <span>🇬🇧</span>
                Beginning my career as a back-end engineer, I then evolved into a fullstack developer allowing me to understand and master the data at each stage.
                Manipulating a large volume of data on a daily basis encouraged me to rely on data visualization to create adapted data views.
                Whether it is for storytelling presentation, a graphic support to convince or a personalized tool to manage information,
                I believe data visualization is now an essential step in the Big Data world.
              </p>
              <p>
                <span>🇫🇷</span>
                Débutant ma carrière en tant qu’ingénieure back-end, j’ai ensuite évolué vers un profil fullstack me permettant de comprendre et maîtriser la donnée à chaque étape.
                Manipuler au quotidien une grande volumétrie de données m’a encouragé à m’appuyer sur la data visualisation pour créer des vues de données adaptées.
                Que ce soit un storytelling pour présenter, un support graphique pour convaincre ou un outil sur-mesure pour gérer les informations,
                la data visualisation est désormais un métier incontournable du Big Data.
              </p>
              <p>
                More about me and my work here : <a href="https://github.com/cecileHBH/aboutme">https://github.com/cecileHBH/aboutme</a>
              </p>
            </div>
          </div>
        </div>
    </div>
</template>
<script>
  export default {
    name: 'Contact',
    props: {
    }
  }
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.section {
  float: right;
  height: 100vh;
  padding-top: 60px;
  width: 100%;
}
.title{
  float: left;
  padding: 0 0 0 250px;
  font-size: 30px;
  text-align: left;
  text-transform: uppercase;
}
.team{
  padding-left: 200px;
  padding-top: 130px;
}
.team-member{
  margin-right: 100px;
  margin-bottom: 100px;
}
.picture{
  width: 500px;
  height: auto;
  float: left;
  margin: 10px;
}
.resume{
  text-align: left;
  padding: 20px;
  margin-left: 550px;
}
/*p::before  {
    content: "\01F354";
}*/
</style>