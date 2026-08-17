<!DOCTYPE html>
<html>
<head>
    <title>Library Management System</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #f5f6fa;
        }

        /* SIDEBAR */
        .sidebar {
            width: 200px;
            height: 100vh;
            background: #07152f;
            color: white;
            position: fixed;
            padding: 10px;
        }

        .logo {
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 30px;
        }

        .menu {
            padding: 12px;
            margin: 5px 0;
            cursor: pointer;
            border-radius: 5px;
        }

        .menu:hover,
        .active {
            background: #2864e8;
        }

        /* MAIN */
        .main {
            margin-left: 220px;
            padding: 25px;
        }

        .top {
            background: white;
            padding: 15px;
            display: flex;
            justify-content: space-between;
            margin-bottom: 25px;
        }

        h1 {
            margin-top: 0;
        }

        /* CARDS */
        .cards {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
        }

        .card {
            background: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px #ddd;
        }

        .number {
            font-size: 28px;
            font-weight: bold;
            margin-top: 10px;
        }

        /* TABLE */
        .box {
            background: white;
            padding: 20px;
            margin-top: 20px;
            border-radius: 8px;
        }

        table {
            width: 100%;
            border-collapse: collapse;
        }

        th, td {
            padding: 12px;
            border-bottom: 1px solid #ddd;
            text-align: left;
        }

        th {
            background: #f1f3f8;
        }

        /* BUTTON */
        button {
            background: #2864e8;
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background: #174bbd;
        }

        input, select {
            padding: 10px;
            width: 100%;
            margin: 8px 0 15px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        /* HIDE PAGES */
        .page {
            display: none;
        }

        .page.show {
            display: block;
        }

        /* RESPONSIVE */
        @media(max-width: 800px) {

            .sidebar {
                width: 170px;
            }

            .main {
                margin-left: 170px;
            }

            .cards {
                grid-template-columns: 1fr 1fr;
            }
        }
    </style>
</head>

<body>

<!-- SIDEBAR -->

<div class="sidebar">

    <div class="logo">
        📚 Library<br>
        Management
    </div>

    <div class="menu active" onclick="showPage('dashboard', this)">
        🏠 Dashboard
    </div>

    <div class="menu" onclick="showPage('books', this)">
        📖 Books
    </div>

    <div class="menu" onclick="showPage('members', this)">
        👥 Members
    </div>

    <div class="menu" onclick="showPage('issue', this)">
        📕 Issue Books
    </div>

    <div class="menu" onclick="showPage('returns', this)">
        🔄 Returns
    </div>

    <div class="menu" onclick="showPage('categories', this)">
        📂 Categories
    </div>

    <div class="menu" onclick="showPage('reports', this)">
        📊 Reports
    </div>

    <div class="menu" onclick="showPage('settings', this)">
        ⚙ Settings
    </div>

</div>


<!-- MAIN CONTENT -->

<div class="main">

    <div class="top">
        <b>Library Management System</b>
        <span>🔔 Admin</span>
    </div>


    <!-- DASHBOARD -->

    <div id="dashboard" class="page show">

        <h1>Dashboard</h1>

        <div class="cards">

            <div class="card">
                <p>Total Books</p>
                <div class="number">1200</div>
                <small>View Details</small>
            </div>

            <div class="card">
                <p>Total Members</p>
                <div class="number">350</div>
                <small>View Details</small>
            </div>

            <div class="card">
                <p>Issued Books</p>
                <div class="number">85</div>
                <small>View Details</small>
            </div>

            <div class="card">
                <p>Returned Books</p>
                <div class="number">1105</div>
                <small>View Details</small>
            </div>

        </div>

        <div class="box">

            <h2>Recent Activities</h2>

            <p>📖 Book "Atomic Habits" issued to John Doe</p>
            <p>📖 Book "The Alchemist" returned</p>
            <p>👤 New member registered</p>
            <p>📖 New book added</p>

        </div>

    </div>


    <!-- BOOKS -->

    <div id="books" class="page">

        <h1>Books</h1>

        <button onclick="showPage('addbook')">
            + Add New Book
        </button>

        <div class="box">

            <table>

                <tr>
                    <th>No</th>
                    <th>Book Title</th>
                    <th>Author</th>
                    <th>Category</th>
                    <th>Quantity</th>
                    <th>Status</th>
                </tr>

                <tr>
                    <td>1</td>
                    <td>Atomic Habits</td>
                    <td>James Clear</td>
                    <td>Self Help</td>
                    <td>5</td>
                    <td>Available</td>
                </tr>

                <tr>
                    <td>2</td>
                    <td>The Alchemist</td>
                    <td>Paulo Coelho</td>
                    <td>Fiction</td>
                    <td>3</td>
                    <td>Available</td>
                </tr>

                <tr>
                    <td>3</td>
                    <td>1984</td>
                    <td>George Orwell</td>
                    <td>Fiction</td>
                    <td>2</td>
                    <td>Issued</td>
                </tr>

            </table>

        </div>

    </div>


    <!-- ADD BOOK -->

    <div id="addbook" class="page">

        <h1>Add New Book</h1>

        <div class="box">

            <label>Book Title</label>
            <input type="text" id="bookTitle"
                   placeholder="Enter book title">

            <label>Author</label>
            <input type="text" id="bookAuthor"
                   placeholder="Enter author name">

            <label>Category</label>
            <select>
                <option>Fiction</option>
                <option>Self Help</option>
                <option>Education</option>
                <option>Technology</option>
            </select>

            <label>Quantity</label>
            <input type="number"
                   placeholder="Enter quantity">

            <button onclick="saveBook()">
                Save Book
            </button>

        </div>

    </div>


    <!-- MEMBERS -->

    <div id="members" class="page">

        <h1>Members</h1>

        <div class="box">

            <table>

                <tr>
                    <th>No</th>
                    <th>Name</th>
                    <th>Email</th>
                    <th>Phone</th>
                </tr>

                <tr>
                    <td>1</td>
                    <td>John Doe</td>
                    <td>john@gmail.com</td>
                    <td>9876543210</td>
                </tr>

                <tr>
                    <td>2</td>
                    <td>Jane Smith</td>
                    <td>jane@gmail.com</td>
                    <td>8765432109</td>
                </tr>

                <tr>
                    <td>3</td>
                    <td>Michael Brown</td>
                    <td>michael@gmail.com</td>
                    <td>7654321098</td>
                </tr>

            </table>

        </div>

    </div>


    <!-- ISSUE BOOK -->

    <div id="issue" class="page">

        <h1>Issue Book</h1>

        <div class="box">

            <label>Member</label>

            <select>
                <option>John Doe</option>
                <option>Jane Smith</option>
                <option>Michael Brown</option>
            </select>

            <label>Book</label>

            <select>
                <option>Atomic Habits</option>
                <option>The Alchemist</option>
                <option>1984</option>
            </select>

            <label>Issue Date</label>
            <input type="date">

            <label>Due Date</label>
            <input type="date">

            <button onclick="issueBook()">
                Issue Book
            </button>

        </div>

    </div>


    <!-- RETURNS -->

    <div id="returns" class="page">

        <h1>Returns</h1>

        <div class="box">

            <table>

                <tr>
                    <th>Book</th>
                    <th>Member</th>
                    <th>Issue Date</th>
                    <th>Return Date</th>
                    <th>Status</th>
                </tr>

                <tr>
                    <td>The Alchemist</td>
                    <td>Jane Smith</td>
                    <td>01 May 2024</td>
                    <td>10 May 2024</td>
                    <td>Returned</td>
                </tr>

                <tr>
                    <td>Atomic Habits</td>
                    <td>John Doe</td>
                    <td>05 May 2024</td>
                    <td>15 May 2024</td>
                    <td>Returned</td>
                </tr>

            </table>

        </div>

    </div>


    <!-- CATEGORIES -->

    <div id="categories" class="page">

        <h1>Categories</h1>

        <div class="box">

            <table>

                <tr>
                    <th>No</th>
                    <th>Category</th>
                    <th>Description</th>
                    <th>Total Books</th>
                </tr>

                <tr>
                    <td>1</td>
                    <td>Fiction</td>
                    <td>Fictional books</td>
                    <td>320</td>
                </tr>

                <tr>
                    <td>2</td>
                    <td>Self Help</td>
                    <td>Self improvement books</td>
                    <td>210</td>
                </tr>

                <tr>
                    <td>3</td>
                    <td>Education</td>
                    <td>Educational books</td>
                    <td>250</td>
                </tr>

            </table>

        </div>

    </div>


    <!-- REPORTS -->

    <div id="reports" class="page">

        <h1>Reports</h1>

        <div class="cards">

            <div class="card">
                📖
                <h3>Books Report</h3>
                <p>View all books</p>
            </div>

            <div class="card">
                👥
                <h3>Members Report</h3>
                <p>View all members</p>
            </div>

            <div class="card">
                📕
                <h3>Issued Books</h3>
                <p>View issued books</p>
            </div>

            <div class="card">
                🔄
                <h3>Returns Report</h3>
                <p>View returned books</p>
            </div>

        </div>

    </div>


    <!-- SETTINGS -->

    <div id="settings" class="page">

        <h1>Settings</h1>

        <div class="box">

            <h2>Profile Information</h2>

            <label>Full Name</label>
            <input type="text" value="Admin User">

            <label>Email</label>
            <input type="email" value="admin@gmail.com">

            <label>Phone</label>
            <input type="text" value="9876543210">

            <button onclick="updateProfile()">
                Update Profile
            </button>

        </div>

    </div>

</div>


<script>

function showPage(pageName, button) {

    let pages = document.getElementsByClassName("page");

    for (let i = 0; i < pages.length; i++) {
        pages[i].classList.remove("show");
    }

    document.getElementById(pageName).classList.add("show");

    let menus = document.getElementsByClassName("menu");

    for (let i = 0; i < menus.length; i++) {
        menus[i].classList.remove("active");
    }

    if (button) {
        button.classList.add("active");
    }
}


function saveBook() {

    let title = document.getElementById("bookTitle").value;
    let author = document.getElementById("bookAuthor").value;

    if (title == "" || author == "") {
        alert("Please enter book details");
    }
    else {
        alert("Book added successfully!");

        document.getElementById("bookTitle").value = "";
        document.getElementById("bookAuthor").value = "";

        showPage("books");
    }
}


function issueBook() {
    alert("Book issued successfully!");
}


function updateProfile() {
    alert("Profile updated successfully!");
}

</script>

</body>
</html>
