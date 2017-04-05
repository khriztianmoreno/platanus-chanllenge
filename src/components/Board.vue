<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <p class="lead">By @khriztianmoreno</p>
    <div class="row">
      <div class="col-md-12">
        <table class="table">
          <thead>
            <tr>
              <th>BID</th>
              <th>BID_SIZE</th>
              <th>ASK</th>
              <th>ASK_SIZE</th>
              <th>BID diff ASK</th>
              <th>BID_SIZE diff ASK_SIZE</th>
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
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Board',
  data() {
    return {
      msg: 'BITCOINS - PLATANUS',
      myBitCoins: [],
    };
  },
  methods: {
    newMetric(valueCoin) {
      if ((valueCoin[1] !== 'hb') && (valueCoin[0] !== '')) {
        // Create new item with formatted
        const bitCointItem = {
          BID: valueCoin[1],
          BID_SIZE: valueCoin[2],
          ASK: valueCoin[3],
          ASK_SIZE: valueCoin[4],
          differenceBidAsk: valueCoin[1] - valueCoin[3],
          differenceBidSizeAskSize: valueCoin[2] - valueCoin[4],
        };

        // Restrict the number of array elements
        if (this.myBitCoins.length > 4) {
          this.myBitCoins.splice(4, 1);
        }

        this.myBitCoins.unshift(bitCointItem);
      }
    },
  },
  mounted() {
    // Source https://developer.mozilla.org/es/docs/WebSockets-840092-dup/Writing_WebSocket_client_applications
    const ws = new WebSocket('wss://api.bitfinex.com/ws/v2');
    const msg = JSON.stringify({
      event: 'subscribe',
      channel: 'ticker',
      symbol: 'tBTCUSD',
    });

    ws.onopen = () => { ws.send(msg); };

    ws.onmessage = (event) => {
      const response = JSON.parse(event.data);
      if (Array.isArray(response)) {
        this.newMetric(response);
      }
    };
  },
};
</script>
