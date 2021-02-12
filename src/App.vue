<template>
  <div id="app">
    <button class="toggleDarkMode" @click="() => toggleDark()">
      <span>{{ darkMode ? "light" : "dark" }}</span>
    </button>
    <!--<button class="toggleEnglish" @click="() => (english = !english)">
      <span>{{ english ? "DE" : "ENG" }}</span>
    </button>-->
    <Heading
      :data="english ? personalEnglish : personalDeutsch"
      :breakpoints="breakpoints"
    />
    <div v-if="english">
      <div v-for="x in eng" :key="x.title">
        <Segment :data="x" :breakpoints="breakpoints" />
      </div>
    </div>
    <div v-else>
      <div v-for="x in de" :key="x.title">
        <Segment :data="x" :breakpoints="breakpoints" />
      </div>
    </div>
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
      darkMode: false,
      english: false,
      breakpoints: {
        xs: window.innerWidth < 360,
        sm: window.innerWidth < 768,
        md: window.innerWidth < 1024,
        lg: window.innerWidth < 1440,
        xl: window.innerWidth >= 1440,
      },
      personalDeutsch: {
        name: "Christopher Kühtz",
        tagline: "Frontend Developer",
        adress: "Nunnenbeckstraße 32",
        city: "90489 Nürnberg",
        mobile: "+4915172109146",
        email: "chriskuehtz@gmail.com",
      },
      de: {
        softwareExperience: {
          title: "Programmier-Erfahrung",
          searchbar: true,
          list: [
            {
              name: "Praktikum bei Codecamp:N",
              daterange: "Okt. 2020 bis Apr. 2021",
              text: [
                "Für sechs Monate arbeite als Frontend Praktikant bei Codecamp:N im Projekt Meine Vorsorgedokumente.",
                "Ich arbeite dort mit Vue.js nach der agilen Scrum Methode.",
                "Aktuell liegt mein Fokus auf der Umsetzung der mobilen Version der Seite und beim Einpflegen einer  SCSS Design Pattern Library.",
                "Auch als Praktikant bin ich vollwertiges Mitglied des Scrum Teams und bearbeite meine eigenen Tickets, z.B. die Umsetzung der Mehrfachauswahl auf der Website.",
              ],
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "SCSS" },
                { text: "Bootstrap" },
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "Vue", icon: "fab fa-vuejs" },
                { text: "Scrum" },
              ],
              links: [
                {
                  http: "https://meine-vorsorgedokumente.de/",
                  name: "Meine Vorsorgedokumente",
                },
              ],
            },
            {
              name: "dev.jetzt Bootcamp",
              text: [
                "Im März 2020 war ich einer der 12 Teilnehmer im dev.jetzt Bootcamp der Firma Mantro in München.",
                "In drei Wochen haben wir einen gesamten Stack von React über Node.js bis zu Postgres Datenbanken kennen gelernt und gleichzeitig viel über Best Practices, Tools und den Alltag in einem Software Unternehmen gelernt.",
              ],
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Bootstrap" },
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
              text: [
                "Auf Entwicklerheld.de löse ich in meiner Freizeit Coding Challenges in fast allen Sprachen und zu verschiedenen Tehmenbereichen. Ich bin (gerade so) unter den Top 100 Nutzern.",
              ],
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
        projects: {
          title: "Web Development Projekte",
          titleSmall: "Web Dev Projekte",
          searchbar: true,
          list: [
            {
              name: "Dieser Lebenslauf",
              text: [
                "Um die Grundlagen von Vue.js zu lernen und um eine dynamische,informative Bewerbung einzureichen, habe ich meinen Lebenslauf als Vue Applikation geschrieben.",
              ],
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
              name: "Groceri",
              text: [
                "Groceri hilft dir, deinen Trip zum Supermarkt effizienter zu gestalten, indem du deine Einkaufsliste in Kategorien(Obst, Fleisch, etc.) einteilst und wöchentliche,monatliche Vorräte automatisch hinzufügen lässt.",
                "So kommst du schneller durch den Einkauf.",
                "Zum ausprobieren kannst du User:guest und Passwort:guest verwenden.",
              ],
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Bootstrap" },
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
              text: [
                "Ich arbeite zusammen mit meiner Freundin an einem Pokemon Spiel, das wir zu zweit spielen können.",
                "Um die Maps für das Spiel zu erstellen, habe ich eine React Application geschrieben.",
                "Applikationen wie diese zeigen, wozu moderne Frontend Frameworks in der Lage sind und das der Browser in gewisser Weise das neue Betriebssystem ist.",
              ],
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
              text: [
                "Das Kampf System für das Pokemon Spiel. Dieses System ist die beste Logik Übung, die ich bis jetzt hatte.",
                "Jede Runde jedes Kampfes muss mit vielen verschiedenen Parametern und Ausnahmefällen trotzdem gleich ablaufen.",
              ],
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Bootstrap" },
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
              text: [
                "Eine kleine Applikation basierend auf meinem Homebrewing Hobby, um die Grundlagen von Angular zu lernen",
              ],
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
        education: {
          title: "Studium",
          list: [
            {
              name:
                "B.Sc. International Production Engineering and Management, FAU Erlangen",
              daterange: "Okt. 2015-Okt. 2019 (ohne Abschluss)",
              text: [
                "2015 habe ich mein Studium im Fach International Production Engineering and Management in Erlangen begonnen.",
                " Nachdem ich Ende 2018 meine Bachelorarbeit mit der Note 1,6 abgeschlossen hatte, habe ich 2019 den letzten Versuch für eine meiner Prüfungen nicht bestanden und musste das Studium ohne Abschluss beenden.",
                "Dieses Ereignis ist die größte Niederlage in meiner Berufs- und Studienlaufbahn.",
                "Ich habe daraus gelernt, dass mein späterer Beruf in einem Feld sein muss, das mir Freude und Erfüllung bringt und zu dem ich voll und ganz stehe.",
                "Deshalb strebe ich jetzt eine Karriere als Software Developer an, da das Programmieren für mich ein klarer Ausdruck meiner Kreativität ist und mir Tag für Tag Spaß macht",
              ],
            },
            {
              name: "B.Sc Mechatronik, FAU Erlangen",
              daterange: "seit Okt. 2019",
              text: [
                "Aktuell studiere ich Mechatronik um meinen Bachelor Abschluss zu erhalten, da ich mir einige Leistungen aus dem vorherigen Studium anrechnen lassen konnte, aber mein Ziel ist eine Karriere als Software Entwickler.",
              ],
            },
          ],
        },
        jobExperience: {
          title: "Arbeitserfahrung",
          titleSmall: "Arbeits-Erfahrung",
          list: [
            {
              name: "Mitarbeiter bei Nosi-Shop.com",
              daterange: "Jan. 2014-Jun.2015",
              text: [
                `nach meinem Abitur 2013 war ich unsicher was ich studieren sollte und habe zusammen mit
                meinem Vater an Nosi-Shop.com, seinem Online-Handel für Sicherheitsartikel und Hausdekorationen
                gearbeitet. Ich war hauptsächlich für die Bestellungsabwicklung und Kommunikation mit Kunden zuständig,
                bis ich 2015 für mein Studium nach Erlangen gezogen bin.`,
              ],
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
      personalEnglish: {
        name: "Christopher Kuhtz",
        tagline: "Frontend Developer",
        adress: "Nunnenbeckstraße 32",
        city: "90489 Nuremberg, Germany",
        mobile: "+4915172109146",
        email: "chriskuehtz@gmail.com",
      },
      eng: {
        softwareExperience: {
          title: "Developer Experience",
          searchbar: true,
          list: [
            {
              name: "Internship Codecamp:N",
              daterange: "Oct. 2020 through Mar. 2021",
              text: `
                I am currently a frontend development intern at Codecamp:N.
                My team develops the vue application for meine-vorsorgedokumente.de using Scrum for workflow managment and Github for version control.
                Meine Vorsorgedokumente allows the user to document their medical and legal preferences in case of an injury that leaves them incapable of expressing their will in person.
                We create valid legal documents, that are accessible 24/7 through our online platform.`,
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "SCSS" },
                { text: "Bootstrap" },
                { text: "Javascript", icon: "fab fa-js-square" },
                { text: "Vue", icon: "fab fa-vuejs" },
                { text: "Scrum" },
              ],
              links: [
                {
                  http: "https://meine-vorsorgedokumente.de/",
                  name: "Meine Vorsorgedokumente",
                },
              ],
            },
            {
              name: "dev.jetzt Bootcamp",
              text: `In march 2020, i was one of 12 participants in mantro's free coding bootcamp dev.jetzt (dev.now).
                Over the course of 3 weeks, we were introduced to `,
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Bootstrap" },
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
        projects: {
          title: "Web Development Projekte",
          titleSmall: "Web Dev Projekte",
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
              name: "Groceri",
              text:
                "Groceri hilft dir, deinen Trip zum Supermarkt effizienter zu gestalten (gerade zur Zeit sehr nützlich), indem du deine Einkaufsliste in Kategorien(Obst, Fleisch, etc.) einteilst und wöchentliche,monatliche Vorräte automatisch hinzufügen lässt. So kommst du schneller durch den Einkauf. Zum ausprobieren kannst du User:guest und Passwort:guest verwenden.",
              skills: [
                { text: "HTML" },
                { text: "CSS", icon: "fab fa-css3-alt" },
                { text: "Bootstrap" },
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
                { text: "Bootstrap" },
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
          titleSmall: "Arbeits-Erfahrung",
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
  methods: {
    toggleDark() {
      this.darkMode = !this.darkMode;
      if (this.darkMode) {
        document.querySelector("body").classList.add("darkMode");
      } else {
        document.querySelector("body").classList.remove("darkMode");
      }
    },
  },
};
</script>

<style>
/*Dark Mode*/
:root {
  --my-color: #2c3e50;
  --my-bg-color: rgb(233, 232, 227);
  --my-accent-color: rgb(168, 14, 40);
}
.darkMode {
  --my-bg-color: #111111;
  --my-color: rgb(235, 231, 215);
  --my-accent-color: rgb(14, 168, 155);
}
body {
  color: var(--my-color);
  background-color: var(--my-bg-color);
}
.toggleDarkMode {
  color: var(--my-color);
  background-color: var(--my-bg-color);
  border: solid 2px var(--my-accent-color);
  border-radius: 0.5rem;
  /*border-bottom-right-radius: 0;
  border-top-right-radius: 0;
  border-right: none;*/
  height: 2rem;
  width: 3rem;
}
.toggleEnglish {
  color: var(--my-color);
  background-color: var(--my-bg-color);
  border: solid 2px var(--my-accent-color);
  border-radius: 0.5rem;
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
  height: 2rem;
  width: 3rem;
}
.toggleDarkMode:focus,
.toggleEnglish:focus {
  outline: none;
}
/*General*/
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding-right: 1rem;
  padding-left: 1rem;
  font-size: 120%;
  max-width: 1440px;
  margin: 0 auto;
}
/*Utilities*/
.order-1 {
  order: 1;
}
.order-2 {
  order: 2;
}
.order-3 {
  order: 3;
}
.accent {
  color: var(--my-accent-color);
}
.w100 {
  width: 100% !important;
}
.center {
  text-align: center;
}
.no-border {
  border: none !important;
}
</style>
