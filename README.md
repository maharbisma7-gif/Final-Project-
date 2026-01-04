# Final-Project-
<!DOCTYPE html>
<html>
<head>
<title>Five Star| Restaurant</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family: Arial, sans-serif;
}

body{
    background:#0b0b0b;
    color:#fff;
}

/* NAVBAR */
nav{
    background:#000;
    padding:20px 50px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

nav h1{
    color:#d4af37;
    letter-spacing:2px;
}

nav a{
    color:#fff;
    margin-left:25px;
    text-decoration:none;
}

nav a:hover{
    color:#d4af37;
}

/* HERO */
.hero{
    height:80vh;
    background:linear-gradient(rgba(0,0,0,.7),rgba(0,0,0,.7)),
    url("https://images.unsplash.com/photo-1552566626-52f8b828add9") center/cover;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
}

.hero h2{
    color:#d4af37;
    font-size:48px;
}

.hero p{
    margin:15px 0;
    color:#ccc;
}

/* SECTION */
.section{
    padding:70px 50px;
    text-align:center;
}

.section h2{
    color:#d4af37;
    margin-bottom:40px;
}

/* MENU */
.menu-container{
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(250px,1fr));
    gap:30px;
}

.menu-card{
    background:#111;
    border:1px solid #d4af37;
    padding:25px;
    transition:.4s;
}

.menu-card:hover{
    transform:translateY(-10px);
    box-shadow:0 0 15px #d4af37;
}

.menu-card h3{
    color:#d4af37;
}

.price{
    margin-top:10px;
    color:#d4af37;
    font-size:18px;
}

/* ORDER FORM */
.order-form{
    max-width:500px;
    margin:0 auto;
    display:flex;
    flex-direction:column;
    gap:15px;
}

.order-form input,
.order-form select,
.order-form textarea{
    padding:12px;
    background:#111;
    border:1px solid #d4af37;
    color:#fff;
}

.order-form button{
    background:#d4af37;
    color:#000;
    padding:12px;
    border:none;
    cursor:pointer;
}

.order-form button:hover{
    background:#b8962e;
}

#msg{
    margin-top:15px;
    color:#d4af37;
}

/* FOOTER */
footer{
    background:#000;
    padding:15px;
    text-align:center;
    color:#aaa;
}
</style>
</head>

<body>

<nav>
    <h1>Five Star Restaurant</h1>
    <div>
        <a href="#Home">Home</a>
        <a href="#menu">Menu</a>
        <a href="#order">Order</a>
        <a href="#Contact">Contact</a>
    </div>
</nav>

<section class="hero">
    <div>
        <h2>Luxury Dining Experience</h2>
        <p>Professional staff, high hygiene standards, and attention to detail make a five-star restaurant a symbol of class, quality, and excellence.</p>
    </div>
</section>

<!-- DYNAMIC MENU -->
<section class="section" id="menu">
    <h2>Our Menu</h2>
    <div class="menu-container" id="menuContainer"></div>
</section>

<!-- ORDER FORM -->
<section class="section" id="order">
    <h2>Order Booking</h2>

    <form class="order-form" id="orderForm">
        <input type="text" id="name" placeholder="Your Name" required>
        <input type="tel" id="phone" placeholder="Phone Number" required>

        <select id="item" required>
            <option value="">Select Item</option>
        </select>

        <input type="number" id="qty" placeholder="Quantity" min="1" required>
        <textarea id="address" placeholder="Delivery Address" required></textarea>

        <button type="submit">Place Order</button>
    </form>

    <p id="msg"></p>
</section>

<footer>
    © 2026 Five Star | Restaurant Project
</footer>

<script>
// MENU DATA
const menuItems = [
    {name:"Grilled Steak", price:"Rs:1250"},
    {name:"Golden Pasta", price:"Rs:1800"},
    {name:"Luxury Burger", price:"Rs:1500"},
    {name:"Royal Biryani", price:"Rs:1220"},
    {name:"Signature Dessert", price:"Rs:2299"}
];

const menuContainer = document.getElementById("menuContainer");
const itemSelect = document.getElementById("item");

// RENDER MENU + SELECT OPTIONS
menuItems.forEach(item=>{
    // menu card
    const card = document.createElement("div");
    card.className="menu-card";
    card.innerHTML = `
        <h3>${item.name}</h3>
        <div class="price">${item.price}</div>
    `;
    menuContainer.appendChild(card);

    // select option
    const option = document.createElement("option");
    option.textContent = item.name;
    itemSelect.appendChild(option);
});

// ORDER FORM
document.getElementById("orderForm").addEventListener("submit",function(e){
    e.preventDefault();

    const name = document.getElementById("name").value;
    const item = document.getElementById("item").value;
    const qty = document.getElementById("qty").value;

    document.getElementById("msg").innerText =
        `Thank you Rs{name}! Your order for Rs{qty} Rs{item}(s) has been booked.`;

    this.reset();
});
</script>

</body>
</html>
In This website I use HTML,CSS and JavaScript "Indulge in exquisite cuisine and exceptional service at [Five Star Restaurant]. Book your table now and elevate your dining experience." 
