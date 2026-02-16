## 📦 Day 5 – CSS Box Model

- Today I learned about the CSS Box Model,
- which is the foundation of layout design in web development.

## ✅ 1️⃣ What is CSS Box Model?
- Every HTML element is treated as a box.

## It consists of:
+------------------------+
|        Margin          |
|  +------------------+  |
|  |     Border       |  |
|  |  +------------+  |  |
|  |  |  Padding   |  |  |
|  |  |  +------+  |  |  |
|  |  |  |Content|  |  |  |
|  |  |  +------+  |  |  |
|  |  +------------+  |  |
|  +------------------+  |
+------------------------+

## ✅ 2️⃣ Margin

-🔹 Space outside the element
-🔹 Creates gap between elements

# Example:
.box {
  margin: 20px;
}

-👉 Adds 20px space outside the element on all sides.

## ✅ 3️⃣ Padding

-🔹 Space inside the element
-🔹 Between content and border

# Example:
.box {
  padding: 15px;
}

-👉 Adds space inside the box.

## ✅ 4️⃣ Border
-🔹 Surrounds padding and content

# Example:

.box {
  border: 2px solid black;
}

You can control:

border-width: 2px;
border-style: solid;
border-color: red;

# ✅ 5️⃣ Width vs Max-Width
#  🔹 width

Fixed width.

.box {
  width: 400px;
}

-⚠️ If screen is smaller, it may overflow.

# 🔹 max-width

Responsive width.

.box {
  max-width: 400px;
}

-👉 Element will shrink on smaller screens.
-👉 Best for responsive design.
-✅ Always prefer max-width for containers.

## ✅ 6️⃣ box-sizing Property
By default:

width = content only

Padding & border are added extra.

## Example (Default: content-box)
.box {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
}

# Actual width becomes:

200 + 20 + 20 + 5 + 5 = 250px

## 🔹 border-box (Recommended)
.box {
  box-sizing: border-box;
}

## Now:

Total width = 200px (including padding & border)

# 🎯 7️⃣ Create Card Layout
## HTML :
<!DOCTYPE html>
<html>
<head>
  <title>Course Cards</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <section class="cards">

    <div class="card">
      <img src="https://img.icons8.com/color/96/java-coffee-cup-logo.png">
      <h3>Java Full Stack</h3>
      <p>Frontend + Backend + Database development.</p>
      <button>Enroll</button>
    </div>

    <div class="card">
      <img src="https://img.icons8.com/color/96/python.png">
      <h3>Python + AI</h3>
      <p>Machine Learning & NLP projects.</p>
      <button>Enroll</button>
    </div>

    <div class="card">
      <img src="https://img.icons8.com/color/96/react-native.png">
      <h3>React JS</h3>
      <p>Modern UI development with hooks & APIs.</p>
      <button>Enroll</button>
    </div>

    <div class="card">
      <img src="https://img.icons8.com/color/96/test-passed.png">
      <h3>Automation Testing</h3>
      <p>Selenium, API Testing & frameworks.</p>
      <button>Enroll</button>
    </div>

    <div class="card">
      <img src="https://img.icons8.com/color/96/amazon-web-services.png">
      <h3>AWS</h3>
      <p>Cloud computing & DevOps fundamentals.</p>
      <button>Enroll</button>
    </div>

    <div class="card">
      <img src="https://img.icons8.com/color/96/net-framework.png">
      <h3>.NET</h3>
      <p>Build enterprise applications using C#.</p>
      <button>Enroll</button>
    </div>

  </section>

</body>
</html>

## CSS :

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, sans-serif;
  background-color: #f2f2f2;
}


.cards {
  max-width: 1100px;
  margin: 50px auto;       
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 25px;               
  padding: 20px;            
}


.card {
  background: white;
  padding: 25px;           
  border: 1px solid #ddd;   
  border-radius: 10px;
  box-shadow: 0 5px 12px rgba(0,0,0,0.08);
  transition: 0.3s ease;
}


.card:hover {
  transform: translateY(-5px);
}


button {
  margin-top: 15px;         
  padding: 10px 15px;       
  border: none;
  background-color: #2563eb;
  color: white;
  border-radius: 6px;
  cursor: pointer;
}

## OUT PUT 
![Day-5 Output](Day-5/img/day-5-output.png)
