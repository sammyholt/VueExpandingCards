<template>
  <div class="container">
    <EventCard
      v-for="(card, index) in cards"
      :key="index"
      :title="card.title"
      :imageURL="card.imageURL"
      :cardNumber="index"
      :isActive="activeCard == index"
      @clicked="cardClicked"
    />
  </div>
</template>

<script>
import EventCard from './EventCard';
export default {
  name: 'EventCards',
  components: {
    EventCard,
  },
  data() {
    return {
      activeCard: 0,
      cards: [
        {
          title: 'Explore the World',
          imageURL:
            'https://images.unsplash.com/photo-1558979158-65a1eaa08691?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
        },
        {
          title: 'Sunny Beach',
          imageURL:
            'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1353&q=80',
        },
        {
          title: 'Wild Forest',
          imageURL:
            'https://images.unsplash.com/photo-1572276596237-5db2c3e16c5d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
        },
        {
          title: 'City on Winter',
          imageURL:
            'https://images.unsplash.com/photo-1551009175-8a68da93d5f9?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1351&q=80',
        },
        {
          title: 'Mountains - Clouds',
          imageURL:
            'https://images.unsplash.com/photo-1549880338-65ddcdfd017b?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80',
        },
      ],
    };
  },
  methods: {
    cardClicked(cardNumber) {
      this.activeCard = cardNumber;
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Muli&display=swap');

* {
  box-sizing: border-box;
}

.panel {
  background-size: cover 100%;
  background-position: center;
  background-repeat: no-repeat;
  height: 80vh;
  border-radius: 50px;
  color: #fff;
  cursor: pointer;
  flex: 0.5;
  margin: 10px;
  position: relative;
  transition: flex 0.7s ease-in;
}

.panel h3 {
  font-size: 24px;
  position: absolute;
  bottom: 20px;
  left: 20px;
  margin: 0;
  opacity: 0;
}

.panel.active {
  flex: 5;
}

.panel.active h3 {
  opacity: 1;
  transition: opacity 0.3s ease-in 0.4s;
}

body {
  font-family: 'Muli', sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  overflow: hidden;
  margin: 0;
}

.container {
  display: flex;
  width: 90vw;
}
.container {
  width: 100vw;
}
@media (max-width: 680px) {
  .panel:nth-of-type(4),
  .panel:nth-of-type(5) {
    display: none;
  }
}
</style>
