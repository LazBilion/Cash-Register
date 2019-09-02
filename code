function checkCashRegister(price, cash, cid) {

  var table =
 {"PENNY":0.01,
  "NICKEL":0.05,
  "DIME":0.1,
  "QUARTER":0.25,
  "ONE":1,
  "FIVE":5,
  "TEN":10,
  "TWENTY":20,
  "ONE HUNDRED":100
 };
  
var remain = cash-price;
var result = {status:"",change:[]};

var totalreg = cid.reduce(function(sum, arr){
return sum + arr[1];
},0);



if (totalreg < remain){
  result.status="INSUFFICIENT_FUNDS";
  return result;
}else if (totalreg === remain){
  return {status: "CLOSED", change: cid};
}else if (totalreg > remain){
  result.status="OPEN";
  var dic = cid.reverse();
  console.log(dic);
  for (var a of dic){
    var n=0;
    var denom=table[a[0]];
    while (remain - denom >=0 && a[1]>0){
      n+=1;
      remain -= denom;
      a[1]=a[1]-denom;
      remain = Math.round(remain*100)/100;
    }
    if (n!==0){
      result.change.push([a[0],n*denom]);
    }
}
console.log(result.status);
console.log(result.change);
console.log(remain)
if (remain >0){
  return {status: "INSUFFICIENT_FUNDS", change: []};
}
console.log(result.status);
console.log(result.change);
return result;
}
}
