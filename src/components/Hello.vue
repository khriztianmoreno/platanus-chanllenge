<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>By @khriztianmoreno</h2>
    <table class="table">
			<thead>
				<tr>
					<th>BID</th>
					<th>BID_SIZE</th>
					<th>ASK</th>
					<th>ASK_SIZE</th>
					<th>BID vs ASK</th>
					<th>BID_S vs ASK_S</th>
					<th>$ BID</th>
					<th>$ ASK</th>
				</tr>
			</thead>
			<tbody>
			</tbody>
		</table>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data() {
    return {
      msg: 'BITCOINS - PLATANUS',
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

</style>
