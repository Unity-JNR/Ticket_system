<template>
    <div v-for="item in $store.state.singleTicket" :key="item.id">
        <h3>Ticket Details</h3>
    <p><strong>TICKET ID:</strong> {{ item.ticket_id }}</p>
    <p><strong>COMPLAINT:</strong> {{ item.complaint }}</p>
    <p><strong>DESCRIPTION:</strong> {{item.description }}</p>
    <p><strong>TICKET:</strong> {{item.ticket }}</p>
    <p><strong>URGENCY:</strong> {{item.urgency }}</p>
    <p><strong>USER ID:</strong> {{item.user_id }}</p>
    <p><router-link to="/dashboard" class="btn btn-dark">Back to Tickets</router-link></p>
    <!-- <button @click="clearTicket">Back to Tickets</button> -->
  </div>
   
</template>
<!-- data() {
  return {
    currYear: new Date().getFullYear(),
    user_email: 'cheslyn@lifechoices.co.za',
    subject: 'Hello from StudioTicketFlow',
    body: 'I wanted to reach out regarding...'
  };
},
computed: {
  mailtoLink() {
    return `mailto:${this.user_email}?subject=${encodeURIComponent(this.subject)}&body=${encodeURIComponent(this.body)}`;
  }
} -->
<script>
    export default {
      computed: {
        viewTicket() {
        this.$store.dispatch("getTicket", this.$route.params.id);
      }
      }  ,
      mounted() {
      this.viewTicket; // Corrected the function invocation
    }
    }
</script>

<style scoped>

</style>