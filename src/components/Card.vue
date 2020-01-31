<template>
      <div className="card">
        <div className="card-name">{this.props.info.name}</div>
        <div className="card-exchange">
          <div className="card-exchange__short">
            {this.props.info.stock_exchange_short}
          </div>
          <div className="card-exchange__symbol">{this.props.info.symbol}</div>
        </div>
        <div className="card-details">
          <div className="card-details__price">{this.props.info.price}</div>
          <div className="card-details__currency">
            {this.props.info.currency}
          </div>
          <div className="card-details__change">
            {this.props.info.day_change}
          </div>
          <div className="card-details__percent">
            ({this.props.info.change_pct}%)
          </div>
        </div>
        <div class="card-date">
          <div class="card-date__last-trading">
            {this.props.info.last_trade_time}
          </div>
          <div class="card-date__timezone">{this.props.info.timezone}</div>
        </div>
      </div>
</template>

<script>
export default {
  name: "Card"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.card {
  display: inline-block;
  padding: 20px;
  margin: 0 20px 20px 0;
  font-size: 14px;
  border: 1px solid #dfe1e5;
  border-radius: 7px;
}
.card-name {
  font-size: 20px;
  color: rgba(0, 0, 0, 0.62);
}
.card-exchange {
  margin: 0 0 10px 0;
  font-size: 0;
}
.card-exchange__short,
.card-exchange__symbol {
  display: inline-block;
  margin: 0 5px 0 0;
  font-size: 16px;
  color: rgba(0, 0, 0, 0.62);
}
.card-details {
  margin: 0 0 10px 0;
  font-size: 0;
}
.card-details__price,
.card-details__currency,
.card-details__change,
.card-details__percent {
  display: inline-block;
  margin: 0 5px 0 0;
  font-size: 16px;
}
.card-details__price {
  margin: 0 7px 0 0;
  font-size: 27px;
  color: rgba(0, 0, 0, 0.87);
}
.card-details__currency {
  font-size: 16px;
  color: rgba(0, 0, 0, 0.62);
}
.reduce {
  color: #d23f31;
}
.increase {
  color: #0f9d58;
}
.card-date {
  margin: 0;
  font-size: 0;
}
.card-date__last-trading,
.card-date__timezone {
  display: inline-block;
  margin: 0 5px 0 0;
  font-size: 12px;
  color: rgba(0, 0, 0, 0.62);
}

.api-reference {
  display: inline-block;
  margin: 70px 5px;
  font-size: 12px;
}
</style>
