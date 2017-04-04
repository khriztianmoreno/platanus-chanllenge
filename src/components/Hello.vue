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
					<th>BID_SIZE vs ASK_SIZE</th>
					<th>$ BID</th>
					<th>$ ASK</th>
				</tr>
			</thead>
			<tbody>
				<tr v-for="item in myBitCoins">
					<td>{{item.BID}}</td>
					<td>{{item.BID_SIZE}}</td>
					<td>{{item.ASK}}</td>
					<td>{{item.ASK_SIZE}}</td>
					<td>{{item.differenceBidAsk}}</td>
					<td>{{item.differenceBidSizeAskSize}}</td>
					<td>{{item.netoBID}}</td>
					<td>{{item.netoASK}}</td>
				</tr>
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
      myBitCoins: [
        {
          BID: 3,
          BID_SIZE: 907.7,
          ASK: 8.304992,
          ASK_SIZE: 907.78,
          differenceBidAsk: 12.48,
          differenceBidSizeAskSize: -57.12,
          netoBID: -0.0592,
          netoASK: 907.88,
        },
        {
          BID: 3,
          BID_SIZE: 907.7,
          ASK: 8.304992,
          ASK_SIZE: 907.78,
          differenceBidAsk: 12.48,
          differenceBidSizeAskSize: -57.12,
          netoBID: -0.0592,
          netoASK: 907.88,
        },
        {
          BID: 3,
          BID_SIZE: 907.7,
          ASK: 8.304992,
          ASK_SIZE: 907.78,
          differenceBidAsk: 12.48,
          differenceBidSizeAskSize: -57.12,
          netoBID: -0.0592,
          netoASK: 907.88,
        },
        {
          BID: 3,
          BID_SIZE: 907.7,
          ASK: 8.304992,
          ASK_SIZE: 907.78,
          differenceBidAsk: 12.48,
          differenceBidSizeAskSize: -57.12,
          netoBID: -0.0592,
          netoASK: 907.88,
        },
        {
          BID: 3,
          BID_SIZE: 907.7,
          ASK: 8.304992,
          ASK_SIZE: 907.78,
          differenceBidAsk: 12.48,
          differenceBidSizeAskSize: -57.12,
          netoBID: -0.0592,
          netoASK: 907.88,
        },
      ],
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
