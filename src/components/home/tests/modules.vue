<template>
  <div class="module-container">
    <div class="heading">
      <p>Modules</p>
      <div class="ellipsis">
        <svg
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <g opacity="0.8">
            <path
              d="M13 12C13 11.4477 12.5523 11 12 11C11.4477 11 11 11.4477 11 12C11 12.5523 11.4477 13 12 13C12.5523 13 13 12.5523 13 12Z"
              stroke="#03293D"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
            <path
              d="M6 12C6 11.4477 5.55228 11 5 11C4.44772 11 4 11.4477 4 12C4 12.5523 4.44772 13 5 13C5.55228 13 6 12.5523 6 12Z"
              stroke="#03293D"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
            <path
              d="M20 12C20 11.4477 19.5523 11 19 11C18.4477 11 18 11.4477 18 12C18 12.5523 18.4477 13 19 13C19.5523 13 20 12.5523 20 12Z"
              stroke="#03293D"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </g>
        </svg>
      </div>
    </div>
    <div class="backlog-items">
      <backlog-item :items="backlogItems" />
    </div>
  </div>
</template>

<script>
import BacklogItem from "../modules/SingleBacklogItem";
export default {
  components: {
    BacklogItem,
  },
  data() {
    return {
      newBacklogItem: "",
      backlogItems: ["Apply gredient colours on the dashboard sidenav"],
    };
  },
  mounted() {
    if (localStorage.backlogs) {
      this.backlogItems = JSON.parse(localStorage.getItem("backlogs"));
    } else {
      localStorage.setItem("backlogs", JSON.stringify(this.backlogItems));
    }
  },
};
</script>

<style scoped>
.heading p {
  text-align: left;
  color: #03293d;
  font-weight: bolder;
  font-size: 1.1rem;
}
.backlog-items {
  /* margin-top: 1rem; */
  border-radius: 0.5rem;
  width: 100%;
  overflow: auto;
}
.backlog-items::-webkit-scrollbar {
  width: 4px !important;
}
.backlog-items::-webkit-scrollbar-track {
  box-shadow: inset 0 0 5px #d3d3d3;
  border-radius: 10px;
}
.backlog-items::-webkit-scrollbar-thumb {
  background: #c0c0c0;
  border-radius: 10px;
}
.backlog-items:first-of-type {
  margin-top: 0;
}
</style>
