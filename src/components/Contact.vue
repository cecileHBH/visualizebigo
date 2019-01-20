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
        <!--<p>
          For a guide and recipes on how to configure / customize this project,<br>
          check out the
          <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
        </p>
        <h3>Installed CLI Plugins</h3>
        <ul>
          <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
          <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
        </ul>
        <h3>Essential Links</h3>
        <ul>
          <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
          <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
          <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
          <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
          <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
        </ul>
        <h3>Ecosystem</h3>
        <ul>
          <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
          <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
          <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
          <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
          <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
        </ul>-->
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