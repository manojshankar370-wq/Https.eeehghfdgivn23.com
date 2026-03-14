<!DOCTYPE html>
<html>
<head>
    <title>Student Activity Tracker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            background-color: #f4f6f9;
        }

        header {
            background-color: #2c3e50;
            color: white;
            padding: 15px;
            text-align: center;
        }

        nav {
            text-align: center;
            margin: 15px;
        }

        button {
            padding: 8px 15px;
            margin: 5px;
            cursor: pointer;
            border: none;
            background-color: #3498db;
            color: white;
            border-radius: 4px;
        }

        button:hover {
            background-color: #2980b9;
        }

        .container {
            width: 80%;
            margin: auto;
        }

        .activity-card {
            background: white;
            padding: 15px;
            margin: 10px 0;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        .completed {
            color: green;
            font-weight: bold;
        }

        .pending {
            color: orange;
            font-weight: bold;
        }

        #activitiesPage {
            display: none;
        }
    </style>
</head>
<body>

<header>
    <h1>Student Activity Tracker</h1>
</header>

<nav>
    <button onclick="showHome()">Home</button>
    <button onclick="showActivities()">Activities</button>
</nav>

<div class="container">

    <!-- Home Page -->
    <div id="homePage">
        <h2>Welcome!</h2>
        <p>Track and manage your academic activities easily.</p>
    </div>

    <!-- Activities Page -->
    <div id="activitiesPage">
        <h2>Activity List</h2>
        <div id="activityList"></div>
    </div>

</div>

<script>
    const activities = [
        {
            id: 1,
            name: "Math Assignment",
            description: "Complete chapter 5 exercises",
            status: "Pending"
        },
        {
            id: 2,
            name: "Science Project",
            description: "Prepare volcano model",
            status: "Pending"
        },
        {
            id: 3,
            name: "English Essay",
            description: "Write essay on climate change",
            status: "Completed"
        }
    ];

    function showHome() {
        document.getElementById("homePage").style.display = "block";
        document.getElementById("activitiesPage").style.display = "none";
    }

    function showActivities() {
        document.getElementById("homePage").style.display = "none";
        document.getElementById("activitiesPage").style.display = "block";
        renderActivities();
    }

    function renderActivities() {
        const list = document.getElementById("activityList");
        list.innerHTML = "";

        activities.forEach(activity => {
            const card = document.createElement("div");
            card.className = "activity-card";

            const statusClass = activity.status === "Completed" ? "completed" : "pending";

            card.innerHTML = `
                <h3>${activity.name}</h3>
                <p>${activity.description}</p>
                <p>Status: <span class="${statusClass}">${activity.status}</span></p>
                ${activity.status === "Pending" 
                    ? `<button onclick="markCompleted(${activity.id})">Mark as Completed</button>` 
                    : ""}
            `;

            list.appendChild(card);
        });
    }

    function markCompleted(id) {
        const activity = activities.find(a => a.id === id);
        if (activity) {
            activity.status = "Completed";
            renderActivities();
        }
    }
</script>

</body>
</html>
