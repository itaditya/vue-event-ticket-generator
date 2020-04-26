<template>
  <div class="ticket">
    <div class="ticket-column-1">
      <div>
        <h6 class="ticket-heading">Event Name</h6>
        <p class="ticket-info">Event Organiser</p>
      </div>
      <div>
        <span class="ticket-price">$20</span>
        <span>&nbsp;/-</span>
      </div>
    </div>
    <div class="ticket-column-2">
      <div class="ticket-qr">
        QR Code
      </div>
      <p class="ticket-code">ID: 8y37343834</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Ticket",
};
</script>

<style scoped>
.ticket {
  background-color: hsl(243.3, 12.5%, 28.2%);
  color: #fff;
  padding: 15px 20px;
  border-radius: 4px;
  display: flex;
  justify-content: space-between;
}

.ticket-column-1 {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-bottom: 5px;
}

.ticket-heading {
  margin: 0;
  font-size: 20px;
  color: hsl(180, 32.3%, 62.9%);
}

.ticket-info {
  margin: 0;
  margin-top: 10px;
}

.ticket-price {
  font-size: 30px;
}

.ticket-column-2 {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.ticket-qr {
  width: 100px;
  height: 100px;
}

.ticket-code {
  margin: 0;
  margin-top: 5px;
}
</style>
