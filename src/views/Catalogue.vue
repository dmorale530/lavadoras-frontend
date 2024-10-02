<script>
import VsudSwitch from "@/components/VsudSwitch.vue";
import ProfileCard from "./components/ProfileCard.vue";
import VsudAvatar from "../components/VsudAvatar.vue";
import sophie from "@/assets/img/kal-visuals-square.jpg";
import marie from "@/assets/img/marie.jpg";
import ivana from "@/assets/img/ivana-square.jpg";
import peterson from "@/assets/img/team-4.jpg";
import nick from "@/assets/img/team-3.jpg";
import img1 from "@/assets/img/home-decor-1.jpg";
import img2 from "@/assets/img/home-decor-2.jpg";
import img3 from "@/assets/img/home-decor-3.jpg";
import team1 from "@/assets/img/team-1.jpg";
import team2 from "@/assets/img/team-2.jpg";
import team3 from "@/assets/img/team-3.jpg";
import team4 from "@/assets/img/team-4.jpg";
import bgImg from "@/assets/img/curved-images/curved14.jpg";
import ProjectsCard from "./components/ProjectOverviewCard.vue";

import setNavPills from "@/assets/js/nav-pills.js";
import setTooltip from "@/assets/js/tooltip.js";

export default {
  name: "ProfileOverview",
  components: {
    VsudSwitch,
    ProfileCard,
    VsudAvatar,
    ProjectsCard,
  },
  data() {
    return {
      showMenu: false,
      sophie,
      marie,
      ivana,
      peterson,
      nick,
      img1,
      team1,
      team2,
      team3,
      team4,
      img2,
      img3,
      bgImg,
    };
  },

  mounted() {
    this.$store.state.isAbsolute = true;
    this.$store.state.isNavFixed = false;
    setNavPills();
    setTooltip();
  },
  beforeUnmount() {
    this.$store.state.isAbsolute = false;
  },
};
</script>

<template>
  <div class="py-4 container-fluid">
    
    <div class="mt-4 row">
      <div class="col-12">
        <div class="mb-4 card">
          <div class="p-3 pb-0 card-header">
            <h6 class="mb-1">Projects</h6>
            <p class="text-sm">Architects design houses</p>
          </div>
          <div class="p-3 card-body">
            <div class="row">
              <div class="mb-4 col-xl-3 col-md-6 mb-xl-3">
                <projects-card
                  :img="img1"
                  :number="2"
                  title="Modern"
                  description="As Uber works through a huge amount of internal
                  management turmoil."
                  :img-team1="team1"
                  title-team1="Elena Morison"
                  :img-team2="team2"
                  title-team2="Ryan Milly"
                  :img-team3="team3"
                  title-team3="Nick Daniel"
                  :img-team4="team4"
                  title-team4="Peterson"
                />
              </div>
              <div class="mb-4 col-xl-3 col-md-6 mb-xl-3">
                <projects-card
                  :img="img2"
                  :number="1"
                  title="Scandinavian"
                  description="Music is something that every person has his or her own
                        specific opinion about."
                  :img-team1="team3"
                  title-team1="Nick Daniel"
                  :img-team2="team4"
                  title-team2="Peterson"
                  :img-team3="team1"
                  title-team3="Elena Morison"
                  :img-team4="team2"
                  title-team4="Ryan Milly"
                />
              </div>
              <div class="mb-4 col-xl-3 col-md-6 mb-xl-3" v-for="i in 30" :key="i">
                <projects-card
                  :img="img3"
                  :number="3"
                  title="Minimalist"
                  description="Different people have different taste, and various types
                        of music."
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
