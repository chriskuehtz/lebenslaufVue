<template>
  <div id="app">
    <Heading />
    <div v-for="x in stuff" :key="x.title"><Segment :data="x" /></div>
  </div>
</template>

<script>
import Heading from "./components/Heading.vue";
import Segment from "./components/Segment.vue";

export default {
  name: "app",
  components: {
    Heading,
    Segment,
  },
  data() {
    return {
      stuff: {
        projects: {
          title: "Web Development Projekte",
          searchbar: true,
          list: [
            {
              name: "Dieser Lebenslauf",
              text:
                "Um die Grundlagen von Vue.js zu lernen und um eine dynamische,informative Bewerbung einzureichen, habe ich meinen Lebenslauf als Vue Applikation geschrieben.",
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "Vue", icon: "fab fa-vuejs" },
              ],
              links: [
                {
                  http: "https://github.com/chriskuehtz/lebenslaufVue",
                  name: "Github",
                },
              ],
            },
            {
              name: "BurgerAI",
              text:
                "burgerai.de (Burger AI) erstellt durch einen 'supervised learning'  Algorithmus ein Burger Rezept aus 6 Zutaten( Algorithmus), lernt durch jedes heruntergeladene Rezept( positives Feedback), welche Zutaten zusammen passen und nutzt das Gelernte für das nächste Rezept( verbesserter Algorithmus). ",
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Bootstrap CSS" },
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "PHP", icon: "fab fa-php" },
                { text: "MySQL" },
              ],
              links: [{ http: "http://burgerai.de", name: "BurgerAI.de" }],
            },
            {
              name: "Groceri",
              text:
                "Groceri hilft dir, deinen Trip zum Supermarkt effizienter zu gestalten (gerade zur Zeit sehr nützlich), indem du deine Einkaufsliste in Kategorien(Obst, Fleisch, etc.) einteilst und wöchentliche,monatliche Vorräte automatisch hinzufügen lässt. So kommst du schneller durch den Einkauf. Zum ausprobieren kannst du User:guest und Passwort:guest verwenden.",
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "React", icon: "fab fa-react" },
                { text: "Netlify JamStack" },
                { text: "FaunaDB" },
              ],
              links: [
                {
                  http: "https://github.com/chriskuehtz/groceri",
                  name: "Github",
                },
                { http: "http://groceri.netlify.app", name: "Groceri" },
              ],
            },
            {
              name: "Pokemon Map Maker",
              text:
                "Ich arbeite zusammen mit meiner Freundin an einem Pokemon Spiel, das wir zu zweit spielen können. Um die Maps für das Spiel zu erstellen, habe ich eine React Application geschrieben. Applikationen wie diese zeigen, wozu moderne Frontend Frameworks in der Lage sind und das der Browser in gewisser Weise das neue Betriebssystem ist.",
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "React", icon: "fab fa-react" },
              ],
              links: [
                {
                  http: "https://github.com/chriskuehtz/pokemonmm",
                  name: "Github",
                },
                {
                  http: "https://pokemonmm.netlify.app",
                  name: "PokemonMapMaker",
                },
              ],
            },
            {
              name: "Pokemon Battle System",
              text:
                "Das Kampf System für das Pokemon Spiel. Dieses System ist die beste Programmierübung, die ich bis jetzt hatte. Jede Runde jedes Kampfes muss mit vielen verschiedenen Parametern und Ausnahmefällen trotzdem gleich ablaufen. ",
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "React", icon: "fab fa-react" },
              ],
              links: [
                {
                  http: "https://github.com/chriskuehtz/pokemonbattlesystem",
                  name: "Github",
                },
                {
                  http: "https://pokemonbattlesystem.netlify.app",
                  name: "PokemonBattleSystem",
                },
              ],
            },
            {
              name: "Hopfengarten",
              text:
                "Eine kleine Applikation basierend auf meinem Homebrewing Hobby, um die Grundlagen von Angular zu lernen",
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Angular", icon: "fab fa-angular" },
                { text: "Javascript", icon: "fab fa-js-square" },
              ],
              links: [
                {
                  http: "https://github.com/chriskuehtz/hopfengarten",
                  name: "Github",
                },
                {
                  http: "https://hopfengarten.netlify.app",
                  name: "Hopfengarten",
                },
              ],
            },
          ],
        },
        softwareExperience: {
          title: "Andere Programmier-Erfahrung",
          list: [
            {
              name: "dev.jetzt Bootcamp",
              text:
                "Im März dieses Jahres war ich einer der 12 Teilnehmer im dev.jetzt Bootcamp der Firma Mantro in München. In drei Wochen haben wir einen gesamten Stack von React über Node.js bis zu Postgres Datenbanken kennen gelernt und gleichzeitig viel über Best Practices, Tools und den Alltag in einem Software Unternehmen gelernt.",
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "React", icon: "fab fa-react" },
                { text: "Node.js", icon: "fab fa-node-js" },
                { text: "Postgres" },
              ],
              links: [
                { http: "https://www.dev.jetzt/teilnehmen", name: "dev.jetzt" },
              ],
            },
            {
              name: "EntwicklerHeld",
              text:
                "Auf Entwicklerheld.de löse ich in meiner Freizeit Coding Challenges in fast allen Sprachen und zu verschiedenen Tehmenbereichen. Ich bin (gerade so) unter den Top 100 Nutzern.",
              skills: [
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "Java", icon: "fab fa-java" },
                { text: "Python", icon: "fab fa-python" },
                { text: "PHP", icon: "fab fa-php" },
                { text: "C++" },
              ],
              links: [
                { http: "https://entwicklerheld.de", name: "Entwicklerheld" },
              ],
            },
          ],
        },
        education: {
          title: "Studium",
          list: [
            {
              name:
                "B.Sc. International Production Engineering and Management, FAU Erlangen",
              daterange: "Okt. 2015-Okt. 2019 (ohne Abschluss)",
              text: `2015 habe ich mein Studium im Fach International Production Engineering and Management
                in Erlangen begonnen. Nachdem ich Ende 2018 meine Bachelorarbeit mit der Note 1,6 abgeschlossen hatte,
                habe ich 2019 den letzten Versuch für eine meiner Prüfungen nicht bestanden und musste das Studium ohne Abschluss beenden.
                Dieses Ereignis ist die größte Niederlage in meiner Berufs- und Studienlaufbahn.
                Ich habe daraus gelernt, dass mein späterer Beruf in einem Feld sein muss,
                das mir Freude und Erfüllung bringt und zu dem ich voll und ganz stehe. Deshalb strebe ich jetzt eine Karriere als Software Developer an, da das Programmieren für mich ein klarer Ausdruck meiner Kreativität ist und mir Tag für Tag Spaß macht`,
            },
            {
              name: "B.Sc Mechatronik, FAU Erlangen",
              daterange: "seit Okt. 2019",
              text:
                "aktuell studiere ich Mechatronik um meinen Bachelor Abschluss zu erhalten, da ich mir einige Leistungen aus dem vorherigen Studium anrechnen lassen konnte, aber mein Ziel ist eine Karriere als Software Entwickler.",
            },
          ],
        },
        jobExperience: {
          title: "Arbeitserfahrung",
          list: [
            {
              name: "Mitarbeiter bei Nosi-Shop.com",
              daterange: "Jan. 2014-Jun.2015",
              text: `nach meinem Abitur 2013 war ich unsicher was ich studieren sollte und habe zusammen mit
                meinem Vater an Nosi-Shop.com, seinem Online-Handel für Sicherheitsartikel und Hausdekorationen
                gearbeitet. Ich war hauptsächlich für die Bestellungsabwicklung und Kommunikation mit Kunden zuständig,
                bis ich 2015 für mein Studium nach Erlangen gezogen bin.`,
            },
            {
              name: "Praktikum bei Roche Diagnostics",
              daterange: "Feb. 2017-Apr.2017",
              text: `Ich habe zwei Monate als Praktikant bei Roche Diagnostics, einem der weltweit größten Hersteller für medizinische Geräte, in der Niederlassung in Sant Cugat, Spanien verbracht. Dort habe ich in der Abteilung Customer Support and Repairs gearbeitet.`,
            },
            {
              name: "Recherche Mitarbeiter bei Future.Ing",
              daterange: "Okt. 2017-Dez.2017",
              text:
                'Als Recherche Mitarbeiter beim Erlanger Start Up "Future.ING" habe ich wissenschaftliche Recherche zum Thema Phase-Change Materials betrieben.',
            },
          ],
        },
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
