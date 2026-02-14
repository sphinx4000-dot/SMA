[1111.html](https://github.com/user-attachments/files/25318590/1111.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SMA Token</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
*{box-sizing:border-box;}
body{margin:0;font-family:Arial,sans-serif;background:#0b1220;color:#fff;}
section{padding:80px 20px;text-align:center}
h1,h2{margin-bottom:20px}
p{line-height:1.7;color:#d0d7e2;max-width:900px;margin:auto}

/* Banner */
.banner{height:100vh;background:url("https://i.ibb.co/gMvwRv57/11.png") center/cover no-repeat;display:flex;align-items:center;justify-content:center;position:relative;}
.banner::after{content:"";position:absolute;inset:0;background:rgba(0,0,0,.65);}
.banner-content{position:relative;z-index:2;text-align:center;padding:20px;}
.banner h1{font-size:52px;}

/* Buttons */
.buttons{margin-top:30px;display:flex;justify-content:center;gap:15px;flex-wrap:wrap;}
.btn{padding:15px 30px;border-radius:14px;font-weight:bold;text-decoration:none;transition:.3s;box-shadow:0 8px 20px rgba(0,0,0,.5);}
.btn:hover{transform:translateY(-4px);}
.btn-site{background:#1e88e5;color:#fff;}
.btn-bsc{background:#f0b90b;color:#000;}
.btn-wallet{background:#7c4dff;color:#fff;border:none;cursor:pointer;}
.btn-buy{background:#ff7043;color:#fff;border:none;cursor:pointer;}

/* Buy Calculator */
.buy-calculator{margin-top:25px;padding:20px;background:#111827;border-radius:18px;max-width:400px;margin-left:auto;margin-right:auto;}
.buy-calculator input{width:70%;padding:12px;border-radius:12px;border:none;margin-bottom:15px;text-align:center;}
.buy-calculator button{padding:12px 25px;border:none;border-radius:12px;background:#ff7043;color:#fff;font-weight:bold;cursor:pointer;}
.buy-calculator p{margin-top:15px;font-size:18px;color:#fdd835;}

/* Cards */
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:20px;margin-top:40px;}
.card{background:#111827;padding:25px;border-radius:18px;box-shadow:0 10px 30px rgba(0,0,0,.4);}

/* Contract Box */
.contract{background:#0f172a;padding:20px;border-radius:14px;word-break:break-all;margin-top:20px;font-size:14px;}

/* Language Buttons */
.lang{position:fixed;top:20px;right:20px;background:#111827;padding:10px 15px;border-radius:12px;cursor:pointer;font-weight:bold;display:flex;gap:10px;}

/* Chart Container */
#tokenChart{max-width:500px;margin:40px auto 0;}

/* Footer */
footer{padding:20px;background:#0b1220;color:#90a4ae;text-align:center;}
</style>
</head>
<body>

<!-- Language Buttons -->
<div class="lang">
  <button onclick="setLang('en')">EN</button>
  <button onclick="setLang('fr')">FR</button>
</div>

<!-- Banner -->
<div class="banner">
  <div class="banner-content">
    <h1 id="title">SMA TOKEN</h1>
    <p id="desc">SMA Token is a community-driven digital asset built on Binance Smart Chain (BSC), designed for gaming, rewards, and interactive platforms.</p>

    <div class="buttons">
      <a href="https://sma-token.io" target="_blank" class="btn btn-site" id="btnWebsite">🌐 Website</a>
      <a href="https://bscscan.com/token/0x63a090c6530F7A190f4f77604FCBF1218273ac24" target="_blank" class="btn btn-bsc" id="btnBsc">🔗 BscScan</a>
      <button class="btn btn-wallet" onclick="connectWallet()" id="btnWallet">🦊 Connect Wallet</button>
    </div>

    <!-- Buy Calculator -->
    <div class="buy-calculator">
      <input type="number" id="bnbInput" placeholder="Enter BNB amount" step="0.0001">
      <button onclick="buySMA()">💰 Buy SMA</button>
      <p id="smaOutput">You will get 0 SMA</p>
    </div>

  </div>
</div>

<!-- About -->
<section>
<h2 id="aboutTitle">About SMA Token</h2>
<p id="aboutText">SMA Token focuses on transparency, low fees, and long-term growth, offering fast transactions and seamless integration with decentralized applications (dApps).</p>
<div class="contract"><b>Contract Address:</b><br>0x63a090c6530F7A190f4f77604FCBF1218273ac24</div>
</section>

<!-- Tokenomics Section -->
<section style="background:#111827">
<h2 id="tokenTitle">Tokenomics</h2>
<canvas id="tokenChart"></canvas>
<div class="cards">
  <div class="card">💰 Total Supply<br><b>5,000,000,000 SMA</b></div>
  <div class="card">📦 Circulating Supply<br><b>4,995,269,927.84 SMA</b></div>
  <div class="card">🔒 Liquidity<br><b>Locked 100% (1 Year)</b></div>
  <div class="card">👨‍💻 Team Tokens<br><b>Locked</b></div>
  <div class="card">🎮 Gaming & Rewards<br><b>40%</b></div>
  <div class="card">🌍 Community & Marketing<br><b>25%</b></div>
</div>
</section>

<!-- Roadmap -->
<section>
<h2 id="roadmapTitle">Roadmap</h2>
<div class="cards">
  <div class="card">🚀 Phase 1<br>Launch & Liquidity Lock</div>
  <div class="card">🎮 Phase 2<br>Games & Rewards</div>
  <div class="card">📈 Phase 3<br>Listings & Marketing</div>
  <div class="card">🌐 Phase 4<br>Expansion & Partnerships</div>
</div>
</section>

<footer>
Powered By BNB Smart Chain<br>
© 2026 SMA Token — All Rights Reserved
</footer>

<script>
// Language content
const content = {
  en:{
    title:"SMA TOKEN",
    desc:"SMA Token is a community-driven digital asset built on Binance Smart Chain (BSC), designed for gaming, rewards, and interactive platforms.",
    aboutTitle:"About SMA Token",
    aboutText:"SMA Token focuses on transparency, low fees, and long-term growth, offering fast transactions and seamless integration with decentralized applications (dApps).",
    tokenTitle:"Tokenomics",
    roadmapTitle:"Roadmap"
  },
  fr:{
    title:"SMA TOKEN",
    desc:"SMA Token est un actif numérique communautaire construit sur Binance Smart Chain (BSC), conçu pour les jeux, les récompenses et les plateformes interactives.",
    aboutTitle:"À propos de SMA Token",
    aboutText:"SMA Token se concentre sur la transparence, les faibles frais et la croissance à long terme, offrant des transactions rapides et une intégration transparente avec les applications décentralisées (dApps).",
    tokenTitle:"Tokenomics",
    roadmapTitle:"Feuille de route"
  }
}

function setLang(lang){
  document.getElementById("title").innerText = content[lang].title;
  document.getElementById("desc").innerText = content[lang].desc;
  document.getElementById("aboutTitle").innerText = content[lang].aboutTitle;
  document.getElementById("aboutText").innerText = content[lang].aboutText;
  document.getElementById("tokenTitle").innerText = content[lang].tokenTitle;
  document.getElementById("roadmapTitle").innerText = content[lang].roadmapTitle;
}

// Connect Wallet
async function connectWallet(){
  if(window.ethereum){
    await ethereum.request({method:'eth_requestAccounts'});
    alert("Wallet Connected ✔");
  }else{
    alert("Please install MetaMask");
  }
}

// SMA Price placeholder in BNB
const smaPriceBNB = 0.0012; // Example

// Buy SMA function
function buySMA(){
  const bnbAmount = parseFloat(document.getElementById("bnbInput").value);
  if(isNaN(bnbAmount) || bnbAmount <=0){
    document.getElementById("smaOutput").innerText="Enter a valid BNB amount";
    return;
  }
  const smaAmount = bnbAmount / smaPriceBNB;
  document.getElementById("smaOutput").innerText=`You will get ${smaAmount.toLocaleString()} SMA`;
  // Redirect to PancakeSwap with SMA contract
  const url = `https://pancakeswap.finance/swap?outputCurrency=0x63a090c6530F7A190f4f77604FCBF1218273ac24&exactAmount=${bnbAmount}`;
  window.open(url,'_blank');
}

// Tokenomics Pie Chart
const ctx = document.getElementById('tokenChart').getContext('2d');
const tokenChart = new Chart(ctx,{
  type:'pie',
  data:{
    labels:['Liquidity','Gaming & Rewards','Community & Marketing','Team Tokens','Development'],
    datasets:[{
      data:[20,40,25,10,5],
      backgroundColor:['#1e88e5','#ff7043','#4caf50','#7c4dff','#fdd835'],
      borderColor:'#0b1220',
      borderWidth:2
    }]
  },
  options:{
    plugins:{legend:{position:'bottom',labels:{color:'#fff',font:{size:14}}}}
  }
});
</script>
</body>
</html>
