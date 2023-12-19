<template>
  <div class="flex-row">
    <div class="tradingview-widget-container" >
      <div ref="tradingviewWidget" class="tradingview-widget-container__widget"></div>
      <!-- <div class="tradingview-widget-copyright">
        <a href="https://www.tradingview.com/" rel="noopener nofollow" target="_blank">
          <span class="blue-text">Track all markets on TradingView</span>
        </a>
      </div> -->
    </div>
    <div class="symbol-dropdown">
      <label for="symbol">Symbol:</label>
      <select id="symbol" v-model="selectedSymbol" @change="updateSymbol">
        <option v-for="symbol in symbols" :key="symbol.value" :value="symbol.value">{{ symbol.label }}</option>
      </select>
    </div>
  </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        selectedSymbol: 'NASDAQ:AAPL', // Default symbol
        symbols: [ // List of symbols for the dropdown
          { label: 'Apple Inc. (AAPL)', value: 'NASDAQ:AAPL' },
          { label: 'Alphabet Inc. (GOOGL)', value: 'NASDAQ:GOOGL' },
          { label: 'Microsoft Corporation (MSFT)', value: 'NASDAQ:MSFT' },
          { label: 'Amazon.com, Inc. (AMZN)', value: 'NASDAQ:AMZN' },
          { label: 'Facebook, Inc. (FB)', value: 'NASDAQ:FB' },
          { label: 'Tesla, Inc. (TSLA)', value: 'NASDAQ:TSLA' },
          { label: 'NVIDIA Corporation (NVDA)', value: 'NASDAQ:NVDA' },
          { label: 'PayPal Holdings, Inc. (PYPL)', value: 'NASDAQ:PYPL' },
          { label: 'Netflix, Inc. (NFLX)', value: 'NASDAQ:NFLX' },
          { label: 'Adobe Inc. (ADBE)', value: 'NASDAQ:ADBE' },
          { label: 'Intel Corporation (INTC)', value: 'NASDAQ:INTC' },
          { label: 'Cisco Systems, Inc. (CSCO)', value: 'NASDAQ:CSCO' },
          { label: 'Comcast Corporation (CMCSA)', value: 'NASDAQ:CMCSA' },
          { label: 'PepsiCo, Inc. (PEP)', value: 'NASDAQ:PEP' },
          { label: 'Starbucks Corporation (SBUX)', value: 'NASDAQ:SBUX' },
          { label: 'The Walt Disney Company (DIS)', value: 'NYSE:DIS' },
          { label: 'Netflix, Inc. (NFLX)', value: 'NASDAQ:NFLX' },
          { label: 'The Home Depot, Inc. (HD)', value: 'NYSE:HD' },
          { label: 'Verizon Communications Inc. (VZ)', value: 'NYSE:VZ' },
          { label: 'QUALCOMM Incorporated (QCOM)', value: 'NASDAQ:QCOM' },
          { label: 'Texas Instruments Incorporated (TXN)', value: 'NASDAQ:TXN' },
          { label: 'Adobe Inc. (ADBE)', value: 'NASDAQ:ADBE' },
          { label: 'Broadcom Inc. (AVGO)', value: 'NASDAQ:AVGO' },
          { label: 'Costco Wholesale Corporation (COST)', value: 'NASDAQ:COST' },
         
          

        ]
      };
    },
    mounted() {
      this.loadTradingViewWidget();
    },
    methods: {
      loadTradingViewWidget() {
        const script = document.createElement('script');
        script.type = 'text/javascript';
        script.src = 'https://s3.tradingview.com/external-embedding/embed-widget-advanced-chart.js';
        script.async = true;
        script.innerHTML = JSON.stringify({
          "autosize": true,
          "symbol": this.selectedSymbol, // Set the initial symbol
          "interval": "D",
          "timezone": "Etc/UTC",
          "theme": "dark",
          "style": "1",
          "locale": "en",
          "enable_publishing": false,
          "allow_symbol_change": true,
          "support_host": "https://www.tradingview.com"
        });
  
        this.$refs.tradingviewWidget.appendChild(script);
      },
      updateSymbol() {
        // Load the widget again with the updated symbol when the dropdown changes
        this.$refs.tradingviewWidget.innerHTML = ''; // Clear the existing widget
        this.loadTradingViewWidget();
      }
    }
  };
  </script>
  
  <style>
  /* Add any custom styles here */

  .symbol-dropdown {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin-bottom: 30px;
  }


  .symbol-dropdown label {
    margin-right: 10px;
  }

  .symbol-dropdown select {
    padding: 5px;
    border-radius: 5px;
  }

  .tradingview-widget-container {
    height: 100%;
    width: 100%;
  }

  .tradingview-widget-container__widget {
    height: 500px;
    width: 100%;
  }

  .flex-row {
    display: flex;
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
   
  }

  .blue-text {
    color: #2196F3;
  }

  @media (max-width: 768px) {
    .tradingview-widget-container__widget {
      width: 100%;
    }

    

    .symbol-dropdown {
      margin-bottom: 20px;
    }

    .symbol-dropdown select {
      width: 100%;
    }

    .flex-row {
      gap: 0;
    }

    .flex-row > * {
      width: 100%;
    }

    .flex-row > *:first-child {
      margin-bottom: 10px;
    }

    .flex-row > *:last-child {
      margin-top: 10px;
    }

    .flex-row > *:not(:last-child) {
      margin-right: 0;
    }

    .flex-row > *:not(:first-child) {
      margin-left: 0;
    }

    .flex-row > *:not(:first-child):not(:last-child) {
      margin: 0;
    }

    .flex-row > *:not(:first-child):not(:last-child) {
      margin: 0;
    }

    .flex-row > *:not(:first-child):not(:last-child) {
      margin: 0;
    }

    .flex-row > *:not(:first-child):not(:last-child) {
      margin: 0;
    }
  }





  </style>
  