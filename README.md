# final1<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1"/>
<title>JKS Group Unified App - Refined</title>
<style>
  body {
    background: #222735;
    color: #fff; font-family: 'Segoe UI', Arial, sans-serif;
    margin: 0; padding: 0;
    min-height: 100vh;
  }
  header, nav {
    display: flex; justify-content: center; gap: 20px;
    background: #1a2136; padding: 16px 0; box-shadow: 0 2px 8px #0007;
    position: sticky; top: 0; z-index: 999;
  }
  header { font-size: 1.65em; color: #00e1ff; font-weight: bold; text-shadow: 0 0 13px #0fccfc88; }
  nav { padding: 10px 0; background: #232b43; }
  nav button {
    background: none; border: 2.5px solid #0fccfc;
    border-radius: 9px; color: #0fccfc;
    font-weight: 700; font-size: 1em; cursor: pointer;
    padding: 12px 22px; transition: 0.3s;
    user-select: none; margin-bottom: 5px;
  }
  nav button:hover, .nav-active {
    background: #0fccfc; color: #202733;
  }
  main { max-width: 1100px; margin: 38px auto 60px; padding: 0 14px; }
  .main-title { text-align: center; font-size: 2.23em; color: #00e1ff;
    margin-bottom: 28px; font-weight: 700; letter-spacing: 2px; }
  .dashboard {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
    gap: 38px 42px; justify-content: center; align-items: center; margin: 0 auto; max-width: 980px;
  }
  .folder-card {
    background: #23273b;
    border: 3px solid #ffe27f;
    border-radius: 12px;
    min-height: 135px;
    min-width: 180px;
    font-weight: 700;
    font-size: 1.17em;
    color: #ffe27f;
    text-align: center;
    cursor: pointer;
    box-shadow: 0 0 14px 3px #fff68d80, 0 8px 26px #11162290;
    padding: 38px 16px 36px 16px;
    transition: 0.33s;
    display: flex; align-items: center; justify-content: center;
    user-select: none;
  }
  .folder-card:hover {
    background: #ffe27f;
    color: #171e29;
    border-color: #0fccfc;
    box-shadow: 0 0 22px 7px #0fccfc99, 0 6px 36px #23536faa;
    transform: scale(1.05);
  }
  .section-title {
    text-align: center; font-size: 1.52em; font-weight: bold;
    margin: 26px auto 18px auto; color: #ffe27f;
    letter-spacing: 1.2px; text-shadow: 0 0 16px #ffe27fc0;
  }
  .service-list, .category-list {
    display: grid; gap: 22px 38px; grid-template-columns: repeat(auto-fit,minmax(200px,1fr));
    justify-content: center; margin-bottom: 24px; margin-top: 18px;
  }
  .service-card, .category-card {
    background: #1c2239;
    border: 2.3px solid #ffe27f;
    border-radius: 11px;
    font-weight: 700; font-size: 1.13em;
    min-height: 80px;
    display: flex; align-items: center; justify-content: center;
    color: #ffe27f; cursor: pointer; text-align: center;
    box-shadow: 0 0 16px 2px #ffeb8490, 0 6px 18px #1e2635a4;
    padding: 26px 10px;
    transition: 0.18s;
  }
  .service-card:hover, .category-card:hover {
    background: #ffe27f;
    color: #222733;
    border-color: #0fccfc;
    box-shadow: 0 0 28px 9px #0fccfc77, 0 9px 38px #18408baa;
    transform: scale(1.08);
  }
  .back-btn {
    background: #ffe27f; color: #252a39; font-weight: 800;
    border: 2.5px solid #ffe27f; border-radius: 14px; padding: 15px 60px;
    font-size: 1.18em; box-shadow: 2px 2px 13px #ffe27f86;
    margin: 38px auto 28px; display: block; width: max-content;
    cursor: pointer; transition: 0.28s;
    user-select: none;
  }
  .back-btn:hover { background: #00e1ff; color: #fff; border-color: #00e1ff; }
  form.contact-form {
    max-width: 480px; margin: 20px auto 40px auto; padding: 25px 26px;
    background: #172440; border-radius: 14px; border: 2px solid #0fccfccc; font-size: 1.08em;
  }
  form.contact-form label { font-weight: 700; margin-bottom: 10px; display: block; color: #aad4fc; }
  form.contact-form input, form.contact-form textarea, form.contact-form select {
    background: #11253b;
    border: 1.5px solid #0fccfab8;
    padding: 13px 17px;
    border-radius: 8px; color: #cddcff; font-size: 16px;
    margin-bottom: 18px; box-sizing: border-box; width: 100%; resize: vertical;
  }
  form.contact-form input:focus, form.contact-form textarea:focus, form.contact-form select:focus {
    outline: none; border-color: #00b6f1; background: #293767;
  }
  form.contact-form button {
    width: 100%; color: #193140; background: #00e1ff;
    font-weight: 900; font-size: 1.18em; border: none;
    border-radius: 12px; padding: 14px 0; cursor: pointer;
    transition: background-color 0.2s;
  }
  form.contact-form button:hover { background: #38edff;}
  .ecom-imgs { display: grid; grid-template-columns: repeat(auto-fit, minmax(115px, 1fr)); gap: 10px; margin-bottom: 15px; }
  .ecom-imgs img { width:100%; height:76px; border-radius: 9px; object-fit: cover; }
  #map { box-shadow: 0 0 40px 15px #0fccfc24; }
  @media (max-width: 900px) {
    .dashboard, .service-list, .category-list { grid-template-columns: 1fr; gap: 18px; }
    .folder-card, .service-card, .category-card { width: 96%; }
    .ecom-imgs { grid-template-columns: 1fr 1fr; }
  }
</style>
</head>
<body>
<header>JKS Group of Business</header>
<nav>
  <button onclick="showPage('dashboard')">Dashboard</button>
  <button onclick="showPage('profile')">Profile</button>
  <button onclick="showPage('wallet')">Wallet</button>
  <button onclick="showPage('orders')">Orders</button>
  <button onclick="showPage('camera')">Camera</button>
  <button onclick="showPage('maps')">Google Maps</button>
</nav>
<main>
  <!-- Dashboard -->
  <section id="dashboard" class="dashboard"></section>

  <!-- Service List -->
  <section id="serviceView" style="display:none;">
    <div class="section-title" id="serviceTitle"></div>
    <div class="service-list" id="serviceList"></div>
    <form class="contact-form" id="contactForm" style="display:none;">
      <h3 id="contactTitle"></h3>
      <label>Name:</label><input type="text" id="userName" required/>
      <label>Mobile Number:</label><input type="tel" id="userPhone" maxlength="10" pattern="[6-9][0-9]{9}" required/>
      <label>Message:</label><textarea id="userMessage" rows="4" required></textarea>
      <button type="button" onclick="submitContactForm()">Submit via WhatsApp</button>
      <button type="button" class="back-btn" onclick="backToServiceList()">Back to Services</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>
  <!-- Events & Catering -->
  <section id="eventsView" style="display:none;">
    <div class="section-title" id="eventsCategoryTitle"></div>
    <div class="category-list" id="eventsCategories"></div>
    <div class="service-list" id="eventsServiceList"></div>
    <form id="eventContactForm" class="contact-form" style="display:none;">
      <h3 id="eventsContactTitle"></h3>
      <label>Name:</label><input id="eventsUserName" type="text" required />
      <label>Mobile Number:</label><input id="eventsUserPhone" type="tel" pattern="[6-9][0-9]{9}" maxlength="10" required />
      <div id="customFields"></div>
      <label>Message:</label><textarea id="eventsUserMessage" rows="4" required></textarea>
      <button type="button" onclick="submitEventsForm()">Submit via WhatsApp</button>
      <button type="button" class="back-btn" onclick="backToEventsCategory()">Back to Category</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>
  <!-- E-commerce -->
  <section id="ecomView" style="display:none;">
    <div class="section-title">My E-commerce</div>
    <div class="category-list" id="ecomCategories"></div>
    <div id="ecomCategoryContent"></div>
    <div id="ecomServiceList"></div>
    <form id="ecomOrderForm" class="contact-form" style="display:none;">
      <h3 id="ecomOrderTitle"></h3>
      <label>Name:</label><input name="name" type="text" required />
      <label>Mobile Number:</label><input name="phone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required/>
      <label>Order Details:</label><textarea name="orderDetails" rows="3" required></textarea>
      <label>Delivery Address:</label><textarea name="address" required></textarea>
      <button type="submit">Submit Order</button>
      <button type="button" class="back-btn" onclick="backToEcomServices()">Back to Services</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>
  <!-- Camera, Maps, Profile, Wallet, Orders -->
  <section id="camera" style="display:none; text-align:center;">
    <h2 class="section-title">Camera</h2>
    <video id="video" autoplay muted playsinline style="max-width: 100%; margin-bottom:14px; border-radius: 12px; border: 2px solid #0fccfc;"></video>
    <br>
    <button onclick="switchCamera()">Switch Camera</button>
    <button onclick="capturePhoto()">Capture Photo</button>
    <div id="photoOutput" style="margin-top:18px;"></div>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>
  <section id="maps" style="display:none; text-align:center;">
    <h2 class="section-title">Google Maps</h2>
    <div id="map" style="max-width: 600px; height: 410px; margin: 20px auto; border-radius: 12px; border: 2.5px solid #0fccfc;"></div>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>
  <section id="profile" style="display:none;">
    <h2 class="section-title">Profile</h2>
    <form class="contact-form">
      <label>Name:</label><input type="text" placeholder="Your name" />
      <label>Email:</label><input type="email" placeholder="your@email.com" />
      <label>Phone Number:</label><input type="tel" placeholder="Mobile number" />
      <label>Address:</label><textarea rows="3" placeholder="Your address"></textarea>
      <button type="button" onclick="alert('Profile saved!')">Save</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>
  <section id="wallet" style="display:none; text-align:center;">
    <h2 class="section-title">Wallet</h2>
    <p>Your wallet balance: <strong>₹0.00</strong></p>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>
  <section id="orders" style="display:none;">
    <h2 class="section-title">Orders</h2>
    <table style="width:100%; background:#212a3e; color:#fff; border-radius: 8px; font-size: 1em; margin-bottom:35px;">
      <tr><th>Order ID</th><th>Product/Service</th><th>Status</th></tr>
      <tr><td>1001</td><td>Pizza</td><td><span style="color: #00ffc0;">Delivered</span></td></tr>
      <tr><td>1002</td><td>Car Wash</td><td><span style="color: #ffe27f;">Pending</span></td></tr>
      <tr><td>1003</td><td>Loan Enquiry</td><td><span style="color: #00c2ff;">In Progress</span></td></tr>
    </table>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>
</main>
<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY"></script>
<script>
const folders = [
  {id:'ecommerce',label:'My E-commerce'}, {id:'events',label:'Events & Catering'},
  {id:'courier',label:'Courier & Ride Booking'}, {id:'job',label:'Job Consultancy & Services'},
  {id:'tours',label:'Tours & Travels'},{id:'realestate',label:'Real Estate & Construction'},
  {id:'investment',label:'Investment & Business'},{id:'loans',label:'Loans & Insurance'},{id:'home',label:'Home Services'}
];
const moduleServices = {
  courier:['Courier Booking','Ride Booking','Tracking','Support','Rental Vehicles'],
  job:['Job Search','Post Resume','Local Jobs','Non-Local Jobs','PG & Hostel','Services Marketplace'],
  tours:['Tour Bookings','Custom & Regular Tours','Stay Booking','Vehicle Booking','Train/Bus/Flight Tickets'],
  realestate:['Buy','Sell','Rent','Key Services','Construction','Industry'],
  investment:['Gold','Silver','Real Estate','Business Opportunity','Mutual Funds'],
  loans:['Loan Enquiry','Car Insurance','Bike Insurance','Housing Loans','Personal Loans','Health Insurance'],
  home:['CC Camera Installation','Computer Repair','Car Wash','Mobile Repair','Chef Services','Bouncers','Bike Mechanic','Car Mechanic','Electrician','Painter','Plumber','Driver']
};
const ecom = {
  Groceries:['Milk','Meat','Fruits','Vegetables','Flowers','Others'],
  Food:['Biriyani','Tiffins','Ice Cream','Pizza','Burgers','Rolls'],
  Pharmacy:['Medicines','Health Products','Supplements','Care Products']
};
const ecomImgs = {
  Groceries: ['groceries','fruits','vegetables','milk','meat','flowers','tomato','carrot','banana','snacks'],
  Food:['pizza','biriyani','ice-cream','tiffin','burger','rolls','dosa','biryani','pasta','fruit'],
  Pharmacy:['pharmacy','medicine','tablet','capsule','syrup','care','first-aid','bandage','mask','prescription']
};
const eventsCategories = {
  package: [
    {name:"Silver (50k -160k)",services:["Decoration","Catering","DJ & Music","Guest House","Chocolate & Cake","Games & Entertainment"]},
    {name:"Gold (150k - 300k)",services:["Decoration","Catering","Photography","Anchor & Actors","Vehicles"]},
    {name:"Diamond (500k - 5M)",services:["Premium Decoration","Luxury Catering","Video & Photography","Celebrity Anchors"]},
    {name:"Platinum (500k - 800k)",services:["Special Decoration","Exclusive Catering","Top DJs","Private Guest House"]}
  ],
  customized:["Decoration","Catering","Photography & Videography","Anchor & Actors","DJ & Singers","Guest House","Chocolate & Cake","Games & Entertainment","Jewellery","Invitation Cards","Vehicles","Return Gifts","Makeup Artist","Mehandi Artist","Clothing & Accessories"],
  premium:["Decoration","Catering","Photography & Videography","Anchor & Actors","DJ & Singers","Guest House","Chocolate & Cake","Games & Entertainment","Jewellery","Invitation Cards","Vehicles","Return Gifts","Makeup Artist","Mehandi Artist","Clothing & Accessories"]
};
let currentModule = '',currentService = '';
// Renders main dashboard
function showPage(page){
  document.querySelectorAll('main > section').forEach(s=>s.style.display='none');
  document.getElementById(page).style.display='block';
  if(page==='dashboard') renderDashboard();
  if(page==='camera') startCamera();
  if(page==='maps') if(!window.mapLoaded){initMap();window.mapLoaded=true;}
}
function renderDashboard(){
  const db=document.getElementById('dashboard'); db.innerHTML='';
  folders.forEach(f=>{
    const d=document.createElement('div');
    d.className='folder-card'; d.textContent=f.label;
    d.onclick=()=>openModule(f.id);
    db.appendChild(d);
  });
}
// For all but events/ecom
function openModule(mod){
  currentModule=mod; currentService='';
  if(mod==='events'){openEventsDashboard();return;}
  if(mod==='ecommerce'){openEcomDashboard();return;}
  let title = folders.filter(f=>f.id==mod)[0]?.label || mod;
  document.getElementById('serviceTitle').textContent=title;
  let sl=document.getElementById('serviceList'); sl.innerHTML='';
  (moduleServices[mod]||[]).forEach(s=>{
    let d=document.createElement('div');
    d.className='service-card'; d.textContent=s; d.onclick=()=>openContactForm(s);
    sl.appendChild(d);
  });
  document.getElementById('serviceView').style.display='block';
}
function openContactForm(service){
  currentService=service;
  document.getElementById('serviceList').style.display='none';
  const form = document.getElementById('contactForm');
  form.style.display='block';
  document.getElementById('contactTitle').textContent='Contact for '+service;
  document.getElementById('userName').value='';
  document.getElementById('userPhone').value='';
  document.getElementById('userMessage').value='';
}
function submitContactForm(){
  let name=document.getElementById('userName').value.trim();
  let phone=document.getElementById('userPhone').value.trim();
  let message=document.getElementById('userMessage').value.trim();
  if(!name||!phone||!message){alert('Enter all details.');return;}
  window.open(`https://wa.me/8977143043?text=Name:${encodeURIComponent(name)}%0APhone:${encodeURIComponent(phone)}%0AService:${encodeURIComponent(currentService)}%0AMessage:${encodeURIComponent(message)}`,'_blank');
}
function backToServiceList(){
  document.getElementById('contactForm').style.display='none';
  document.getElementById('serviceList').style.display='grid';
}
// ------------------ Events & Catering ------------------
function openEventsDashboard(){
  document.getElementById('eventsView').style.display='block';
  document.getElementById('eventsCategories').innerHTML='';
  Object.keys(eventsCategories).forEach(cat=>{
    let d=document.createElement('div');
    d.className='category-card';
    d.textContent=cat.charAt(0).toUpperCase()+cat.slice(1);
    d.onclick=()=>openEventsCategory(cat);
    document.getElementById('eventsCategories').appendChild(d);
  });
  document.getElementById('eventsServiceList').innerHTML='';
  document.getElementById('eventContactForm').style.display='none';
  document.getElementById('eventsCategoryTitle').textContent='Events & Catering Categories';
}
function openEventsCategory(cat){
  document.getElementById('eventsServiceList').style.display='grid';
  document.getElementById('eventContactForm').style.display='none';
  document.getElementById('eventsServiceList').innerHTML='';
  document.getElementById('eventsCategoryTitle').textContent = cat.charAt(0).toUpperCase() + cat.slice(1) + ' Services';
  if(cat==='package'){
    eventsCategories.package.forEach(pkg=>{
      let d=document.createElement('div');
      d.className='service-card';
      d.style.width='260px'; d.textContent=pkg.name;
      d.onclick=()=>openPackageServices(pkg.name,pkg.services);
      document.getElementById('eventsServiceList').appendChild(d);
    });
  }else{
    eventsCategories[cat].forEach(s=>{
      let d=document.createElement('div');
      d.className='service-card';
      d.style.width='200px';
      d.textContent=s;
      d.onclick=()=>openEventContactForm(s,cat);
      document.getElementById('eventsServiceList').appendChild(d);
    });
  }
}
function openPackageServices(pkg,arr){
  document.getElementById('eventsCategoryTitle').textContent=pkg+' Services';
  let esl=document.getElementById('eventsServiceList');
  esl.innerHTML='';
  arr.forEach(s=>{
    let d=document.createElement('div');
    d.className='category-card'; d.textContent=s; d.style.width='220px';
    d.onclick=()=>openEventContactForm(s,pkg);
    esl.appendChild(d);
  });
}
function openEventContactForm(s,cat){
  document.getElementById('eventsServiceList').style.display='none';
  document.getElementById('eventContactForm').style.display='block';
  document.getElementById('eventsContactTitle').textContent='Contact for '+s;
  document.getElementById('eventsUserName').value='';
  document.getElementById('eventsUserPhone').value='';
  document.getElementById('eventsUserMessage').value='';
  // Only Customized asks budget&capacity
  document.getElementById('customFields').innerHTML = (cat==='customized')
    ? `<label>Budget:</label>
        <select id="eventsBudget"><option value="">Select</option><option>10k-50k</option><option>50k-1L</option><option>1L-5L</option><option>Above 5L</option></select>
        <label>Capacity:</label>
        <select id="eventsCapacity"><option value="">Select</option><option>5-50 people</option><option>50-150 people</option><option>Above 150 people</option></select>`
    : '';
  document.getElementById('eventsUserName').dataset.cat = cat;
  document.getElementById('eventsUserName').dataset.serv = s;
}
function submitEventsForm(){
  const name=document.getElementById('eventsUserName').value.trim();
  const phone=document.getElementById('eventsUserPhone').value.trim();
  const message=document.getElementById('eventsUserMessage').value.trim();
  const budget=document.getElementById('eventsBudget')?.value||'';
  const capacity=document.getElementById('eventsCapacity')?.value||'';
  const cat=document.getElementById('eventsUserName').dataset.cat;
  const serv=document.getElementById('eventsUserName').dataset.serv;
  if(!name||!phone||!message){alert('Please fill all details!');return;}
  let msg = `Name:${encodeURIComponent(name)}%0APhone:${encodeURIComponent(phone)}%0AService:${encodeURIComponent(serv)}%0ACategory:${encodeURIComponent(cat)}%0AMessage:${encodeURIComponent(message)}`;
  if(budget) msg+=`%0ABudget:${encodeURIComponent(budget)}`;
  if(capacity) msg+=`%0ACapacity:${encodeURIComponent(capacity)}`;
  window.open(`https://wa.me/8977143043?text=${msg}`,'_blank');
}
function backToEventsCategory(){
  document.getElementById('eventContactForm').style.display='none';
  document.getElementById('eventsServiceList').style.display='grid';
}
// ----------------- E-commerce -----------------
function openEcomDashboard(){
  document.getElementById('ecomCategories').innerHTML='';
  Object.keys(ecom).forEach(cat=>{
    let d=document.createElement('div');
    d.className='category-card';d.textContent=cat;d.onclick=()=>openEcomCategory(cat);
    document.getElementById('ecomCategories').appendChild(d);
  });
  document.getElementById('ecomCategoryContent').innerHTML='';
  document.getElementById('ecomServiceList').innerHTML='';
  document.getElementById('ecomOrderForm').style.display='none';
  showPage('ecomView');
}
function openEcomCategory(cat){
  document.getElementById('ecomCategoryContent').innerHTML='<div class="ecom-imgs">'+ecomImgs[cat].map(label=>`<img src="https://source.unsplash.com/150x100/?${label}" alt="${label}"/>`).join('')+'</div>';
  document.getElementById('ecomServiceList').innerHTML='';
  ecom[cat].forEach(subcat=>{
    let d=document.createElement('div');
    d.className='service-card';d.textContent=subcat;d.onclick=()=>openEcomOrderForm(cat,subcat);
    document.getElementById('ecomServiceList').appendChild(d);
  });
  document.getElementById('ecomOrderForm').style.display='none';
}
function openEcomOrderForm(cat,subcat){
  document.getElementById('ecomOrderForm').style.display='block';
  document.getElementById('ecomOrderTitle').textContent=`Order ${subcat} in ${cat}`;
  document.getElementById('ecomOrderForm').onsubmit=function(e){e.preventDefault();submitOrderForm(e,cat,subcat);}
}
function backToEcomServices(){
  document.getElementById('ecomOrderForm').style.display='none';
  document.getElementById('ecomServiceList').style.display='grid';
}
function submitOrderForm(e,cat,subcat){
  const form=e.target;
  const name=form.name.value.trim();
  const phone=form.phone.value.trim();
  const orderDetails=form.orderDetails.value.trim();
  const address=form.address.value.trim();
  if(!name||!phone||!orderDetails||!address){
    alert('All fields required.');return;
  }
  let msg=`Order from JKS E-commerce%0ACategory: ${cat}%0AProduct: ${subcat}%0AName: ${name}%0APhone: ${phone}%0AOrder: ${orderDetails}%0AAddress: ${address}`;
  window.open(`https://wa.me/8977143043?text=${msg}`,'_blank');
}
// Camera & Maps
let currentStream=null,usingFrontCamera=true;
function startCamera() {
  const video=document.getElementById('video');
  if(currentStream){currentStream.getTracks().forEach(track=>track.stop());}
  navigator.mediaDevices.getUserMedia({video:{facingMode:usingFrontCamera?'user':'environment'}})
    .then(stream=>{currentStream=stream;video.srcObject=stream;video.play();})
    .catch(()=>alert('Camera unavailable.'));
}
function switchCamera(){usingFrontCamera=!usingFrontCamera;startCamera();}
function capturePhoto(){
  const video=document.getElementById('video'),canvas=document.createElement('canvas');
  canvas.width=video.videoWidth;canvas.height=video.videoHeight;
  const ctx=canvas.getContext('2d');ctx.drawImage(video,0,0);
  document.getElementById('photoOutput').innerHTML=`<img src="${canvas.toDataURL()}" style="max-width:300px;border-radius:8px;">`;
}
function initMap(){
  new google.maps.Map(document.getElementById('map'),{center:{lat:17.3850,lng:78.4867},zoom:13});
}
document.addEventListener('DOMContentLoaded',()=>showPage('dashboard'));
</script>
<script async defer src="https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY"></script>
</body>
</html>
