<template>
  <div id="app">
    <div class="tickets-control no-print">
      <form class="tickets-form">
        <label>
          <span>Enter Event Name</span>
          <input v-model="eventName" placeholder="Eg: Vue.js Workshop">
        </label>
        <label>
          <span>Enter Event Organiser</span>
          <input v-model="eventOrganizer" placeholder="Eg: Mozilla Bbsr">
        </label>
        <label>
          <span>Enter Event Price</span>
          <input v-model="eventPrice" placeholder="Eg: 20">
        </label>
      </form>
      <div>
        <p>Fill the event details in the form.
          <br>If you like the generated tickets then click on Print button
        </p>
        <button v-on:click="generateTickets">Print Tickets</button>
      </div>
    </div>
    <ul class="tickets-list">
      <li v-for="ticket in tickets" :key="ticket.id">
        <div class="ticket-wrapper">
          <Ticket :event="event" :ticket="ticket"/>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import Ticket from "./components/Ticket";

export default {
  name: "App",
  components: {
    Ticket
  },
  data() {
    return {
      eventName: "Vue.js Workshop",
      eventOrganizer: "Mozilla BBSR",
      eventPrice: "20",
      tickets: [
        {
          id: "ankgeehuge"
        },
        {
          id: "nfghkgeegb"
        },
        {
          id: "sfbhjegebui"
        },
        {
          id: "wihurgbhgef"
        }
      ]
    };
  },
  computed: {
    event() {
      const event = {
        name: this.eventName,
        organiser: this.eventOrganizer,
        price: this.eventPrice
      };

      return event;
    }
  },
  methods: {
    generateTickets() {
      window.print();
    }
  }
};
</script>

<style>
body,
ul,
p,
h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
  padding: 0;
}

* {
  box-sizing: border-box;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.tickets-control {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 40px;
}

.tickets-form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.tickets-list {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
}

.ticket-wrapper {
  width: 340px;
  padding: 5px;
}

@media print {
  body {
    -webkit-print-color-adjust: exact;
  }

  .no-print,
  .no-print * {
    display: none !important;
  }
}
</style>
