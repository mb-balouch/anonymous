<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🌈 Payroll Pro - Employee Management System (Pakistan)</title>
    
    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    
    <style>
        /* ===== ROOT VARIABLES ===== */
        :root {
            --primary: #006600; /* Pakistan Green */
            --secondary: #C0A062; /* Pakistan Gold */
            --dark: #2C3E50;
            --light: #F8F9FA;
            --gradient-1: linear-gradient(135deg, #006600 0%, #C0A062 100%);
            --shadow: 0 10px 30px rgba(0,0,0,0.1);
            --radius: 15px;
        }
        
        /* ===== RESET & BASE ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: all 0.3s ease;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #f5f5f5 0%, #e8e8e8 100%);
            color: var(--dark);
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* ===== HEADER ===== */
        header {
            background: white;
            border-radius: var(--radius);
            padding: 25px;
            margin-bottom: 30px;
            box-shadow: var(--shadow);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            border-left: 5px solid var(--primary);
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo i {
            font-size: 2.5rem;
            color: var(--primary);
        }
        
        .logo h1 {
            font-size: 1.8rem;
            color: var(--primary);
        }
        
        .logo .pk-flag {
            font-size: 1.5rem;
            color: #006600;
        }
        
        .user-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--gradient-1);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        /* ===== NAVIGATION ===== */
        nav {
            background: white;
            border-radius: var(--radius);
            padding: 15px;
            margin-bottom: 30px;
            box-shadow: var(--shadow);
        }
        
        .nav-tabs {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            list-style: none;
        }
        
        .nav-tabs li {
            flex: 1;
            min-width: 120px;
        }
        
        .nav-tabs a {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 15px;
            text-decoration: none;
            color: var(--dark);
            border-radius: 10px;
            text-align: center;
            gap: 8px;
        }
        
        .nav-tabs a:hover {
            background: rgba(0, 102, 0, 0.1);
            transform: translateY(-3px);
        }
        
        .nav-tabs a.active {
            background: var(--gradient-1);
            color: white;
        }
        
        .nav-tabs i {
            font-size: 1.5rem;
        }
        
        /* ===== MAIN CONTENT ===== */
        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .tab-content.active {
            display: block;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* ===== DASHBOARD ===== */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .stat-card {
            background: white;
            padding: 25px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-left: 5px solid var(--primary);
        }
        
        .stat-info h3 {
            color: #666;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 5px;
        }
        
        .stat-info h2 {
            font-size: 2rem;
            font-weight: 700;
        }
        
        .stat-info .currency {
            color: #006600;
            font-weight: bold;
        }
        
        .stat-icon {
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: white;
            background: var(--primary);
        }
        
        .charts {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .chart-card {
            background: white;
            padding: 25px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
        }
        
        .chart-card h3 {
            margin-bottom: 20px;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        /* ===== FORMS ===== */
        .form-card {
            background: white;
            padding: 30px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            margin-bottom: 30px;
        }
        
        .form-card h2 {
            margin-bottom: 25px;
            color: var(--primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .form-row {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: #555;
        }
        
        input, select, textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            font-family: 'Poppins', sans-serif;
        }
        
        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--primary);
        }
        
        .btn {
            padding: 12px 25px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s ease;
        }
        
        .btn-primary {
            background: var(--primary);
            color: white;
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 102, 0, 0.3);
        }
        
        .btn-success {
            background: var(--secondary);
            color: white;
        }
        
        .btn-group {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
        }
        
        /* ===== TABLES ===== */
        .table-container {
            background: white;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            overflow: hidden;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        thead {
            background: var(--primary);
            color: white;
        }
        
        th, td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid #eee;
        }
        
        tbody tr:hover {
            background-color: rgba(0, 102, 0, 0.05);
        }
        
        .badge {
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: 600;
            display: inline-block;
        }
        
        .badge-success { background: #d4edda; color: #155724; }
        .badge-warning { background: #fff3cd; color: #856404; }
        .badge-danger { background: #f8d7da; color: #721c24; }
        .badge-pk { background: var(--primary); color: white; }
        
        .action-buttons {
            display: flex;
            gap: 8px;
        }
        
        .action-btn {
            width: 35px;
            height: 35px;
            border-radius: 50%;
            border: none;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            font-size: 0.9rem;
            color: white;
        }
        
        .edit-btn { background: var(--primary); }
        .delete-btn { background: var(--secondary); }
        .view-btn { background: var(--primary); }
        
        /* ===== MODAL ===== */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }
        
        .modal-content {
            background: white;
            border-radius: var(--radius);
            padding: 30px;
            max-width: 500px;
            width: 100%;
            max-height: 80vh;
            overflow-y: auto;
            position: relative;
            animation: modalSlide 0.3s ease;
        }
        
        @keyframes modalSlide {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #666;
        }
        
        /* ===== NOTIFICATIONS ===== */
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 25px;
            border-radius: 8px;
            color: white;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 10px;
            z-index: 1001;
            animation: slideInRight 0.3s ease;
        }
        
        @keyframes slideInRight {
            from { transform: translateX(100%); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }
        
        .notification.success { background: var(--primary); }
        .notification.error { background: var(--secondary); }
        .notification.info { background: var(--primary); }
        
        /* ===== PAKISTAN THEME ELEMENTS ===== */
        .pk-theme {
            color: var(--primary);
            font-weight: bold;
        }
        
        .currency-pkr {
            font-weight: bold;
            color: var(--primary);
        }
        
        .flag-icon {
            display: inline-block;
            width: 20px;
            height: 15px;
            background: linear-gradient(to right, #006600 33%, white 33%, white 66%, #006600 66%);
            position: relative;
            margin-right: 5px;
        }
        
        .flag-icon:after {
            content: "★";
            position: absolute;
            left: 8px;
            top: 2px;
            color: white;
            font-size: 10px;
        }
        
        /* ===== RESPONSIVE ===== */
        @media (max-width: 768px) {
            .nav-tabs li { min-width: 100px; }
            .nav-tabs a { padding: 10px; }
            .stats-grid { grid-template-columns: 1fr; }
            .charts { grid-template-columns: 1fr; }
            .form-row { grid-template-columns: 1fr; }
            table { display: block; overflow-x: auto; }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- HEADER -->
        <header>
            <div class="logo">
                <i class="fas fa-money-check-alt"></i>
                <h1>Payroll Pro <span class="pk-flag">🇵🇰</span></h1>
            </div>
            <div class="user-info">
                <div class="avatar">
                    <span>AD</span>
                </div>
                <div>
                    <h3>Admin User</h3>
                    <p style="color: #666; font-size: 0.9rem;">System Administrator</p>
                </div>
            </div>
        </header>

        <!-- NAVIGATION -->
        <nav>
            <ul class="nav-tabs">
                <li><a href="#dashboard" class="nav-link active" onclick="showTab('dashboard')">
                    <i class="fas fa-tachometer-alt"></i>
                    <span>Dashboard</span>
                </a></li>
                <li><a href="#employees" class="nav-link" onclick="showTab('employees')">
                    <i class="fas fa-users"></i>
                    <span>Employees</span>
                </a></li>
                <li><a href="#payroll" class="nav-link" onclick="showTab('payroll')">
                    <i class="fas fa-file-invoice-dollar"></i>
                    <span>Payroll</span>
                </a></li>
                <li><a href="#attendance" class="nav-link" onclick="showTab('attendance')">
                    <i class="fas fa-calendar-check"></i>
                    <span>Attendance</span>
                </a></li>
                <li><a href="#departments" class="nav-link" onclick="showTab('departments')">
                    <i class="fas fa-building"></i>
                    <span>Departments</span>
                </a></li>
            </ul>
        </nav>

        <!-- MAIN CONTENT AREA -->
        <main>
            <!-- DASHBOARD TAB -->
            <div id="dashboard" class="tab-content active">
                <div class="stats-grid">
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Total Employees</h3>
                            <h2 id="totalEmployees">4</h2>
                            <p style="color: #666; font-size: 0.9rem;">Pakistan Team</p>
                        </div>
                        <div class="stat-icon">
                            <i class="fas fa-users"></i>
                        </div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Monthly Payroll</h3>
                            <h2><span class="flag-icon"></span><span id="monthlyPayroll">1,520,000</span> PKR</h2>
                            <p style="color: #666; font-size: 0.9rem;">Processing on 28th</p>
                        </div>
                        <div class="stat-icon">
                            <i class="fas fa-money-bill-wave"></i>
                        </div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Departments</h3>
                            <h2 id="totalDepartments">4</h2>
                            <p style="color: #666; font-size: 0.9rem;">Active Departments</p>
                        </div>
                        <div class="stat-icon">
                            <i class="fas fa-building"></i>
                        </div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-info">
                            <h3>Today's Attendance</h3>
                            <h2 id="todayAttendance">3/4</h2>
                            <p style="color: #666; font-size: 0.9rem;">1 on leave</p>
                        </div>
                        <div class="stat-icon">
                            <i class="fas fa-calendar-day"></i>
                        </div>
                    </div>
                </div>

                <div class="charts">
                    <div class="chart-card">
                        <h3><i class="fas fa-chart-pie" style="color: #006600;"></i> Department Distribution</h3>
                        <canvas id="deptChart" width="400" height="250"></canvas>
                    </div>
                    <div class="chart-card">
                        <h3><i class="fas fa-chart-line" style="color: #006600;"></i> Monthly Payroll Trend</h3>
                        <canvas id="payrollChart" width="400" height="250"></canvas>
                    </div>
                </div>

                <div class="form-card">
                    <h2><i class="fas fa-bolt" style="color: #006600;"></i> Quick Actions</h2>
                    <div class="btn-group">
                        <button class="btn btn-primary" onclick="showModal('addEmployeeModal')">
                            <i class="fas fa-user-plus"></i> Add Employee
                        </button>
                        <button class="btn btn-success" onclick="showTab('payroll')">
                            <i class="fas fa-calculator"></i> Process Payroll
                        </button>
                        <button class="btn btn-primary" onclick="showTab('attendance')">
                            <i class="fas fa-clipboard-check"></i> Mark Attendance
                        </button>
                        <button class="btn btn-success" onclick="showModal('addDeptModal')">
                            <i class="fas fa-plus-circle"></i> Add Department
                        </button>
                    </div>
                </div>
            </div>

            <!-- EMPLOYEES TAB -->
            <div id="employees" class="tab-content">
                <div class="form-card">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px;">
                        <h2><i class="fas fa-users" style="color: #006600;"></i> Employee Management</h2>
                        <button class="btn btn-primary" onclick="showModal('addEmployeeModal')">
                            <i class="fas fa-user-plus"></i> Add New Employee
                        </button>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <input type="text" id="searchEmployee" placeholder="🔍 Search employees by name, department..." 
                                   onkeyup="filterEmployeeTable()" style="padding-left: 40px;">
                        </div>
                    </div>
                </div>

                <div class="table-container">
                    <table id="employeeTable">
                        <thead>
                            <tr>
                                <th>ID</th>
                                <th>Employee</th>
                                <th>Department</th>
                                <th>Position</th>
                                <th>Salary (PKR)</th>
                                <th>Status</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="employeeTableBody">
                            <!-- Employee data will be loaded here -->
                        </tbody>
                    </table>
                </div>
            </div>

            <!-- PAYROLL TAB -->
            <div id="payroll" class="tab-content">
                <div class="form-card">
                    <h2><i class="fas fa-file-invoice-dollar" style="color: #006600;"></i> Payroll Processing</h2>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label>Select Employee</label>
                            <select id="payrollEmployee">
                                <option value="">-- Select Employee --</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>Month</label>
                            <select id="payrollMonth">
                                <option value="1">January</option>
                                <option value="2">February</option>
                                <option value="3">March</option>
                                <option value="4">April</option>
                                <option value="5">May</option>
                                <option value="6">June</option>
                                <option value="7">July</option>
                                <option value="8">August</option>
                                <option value="9">September</option>
                                <option value="10">October</option>
                                <option value="11">November</option>
                                <option value="12">December</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>Year</label>
                            <input type="number" id="payrollYear" value="2024" min="2020" max="2030">
                        </div>
                        <div class="form-group" style="align-self: flex-end;">
                            <button class="btn btn-success" onclick="calculatePayroll()" style="width: 100%;">
                                <i class="fas fa-calculator"></i> Calculate Payroll
                            </button>
                        </div>
                    </div>
                </div>

                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Payroll ID</th>
                                <th>Employee</th>
                                <th>Month</th>
                                <th>Basic Salary</th>
                                <th>Allowances</th>
                                <th>Deductions</th>
                                <th>Net Salary</th>
                                <th>Status</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="payrollTableBody">
                            <!-- Payroll data will be loaded here -->
                        </tbody>
                    </table>
                </div>
            </div>

            <!-- ATTENDANCE TAB -->
            <div id="attendance" class="tab-content">
                <div class="form-card">
                    <h2><i class="fas fa-calendar-check" style="color: #006600;"></i> Attendance Management</h2>
                    <div class="form-row">
                        <div class="form-group">
                            <label>Date</label>
                            <input type="date" id="attendanceDate" value="">
                        </div>
                        <div class="form-group">
                            <label>Select Employee</label>
                            <select id="attendanceEmployee">
                                <option value="">-- Select Employee --</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label>Status</label>
                            <select id="attendanceStatus">
                                <option value="Present">✅ Present</option>
                                <option value="Absent">❌ Absent</option>
                                <option value="Half-day">🕐 Half-day</option>
                                <option value="Leave">🏖️ Leave</option>
                            </select>
                        </div>
                        <div class="form-group" style="align-self: flex-end;">
                            <button class="btn btn-primary" onclick="markAttendance()">
                                <i class="fas fa-check-circle"></i> Mark Attendance
                            </button>
                        </div>
                    </div>
                </div>

                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>Date</th>
                                <th>Employee</th>
                                <th>Department</th>
                                <th>Status</th>
                                <th>Check-in</th>
                                <th>Check-out</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="attendanceTableBody">
                            <!-- Attendance data will be loaded here -->
                        </tbody>
                    </table>
                </div>
            </div>

            <!-- DEPARTMENTS TAB -->
            <div id="departments" class="tab-content">
                <div class="form-card">
                    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 20px;">
                        <h2><i class="fas fa-building" style="color: #006600;"></i> Department Management</h2>
                        <button class="btn btn-primary" onclick="showModal('addDeptModal')">
                            <i class="fas fa-plus-circle"></i> Add Department
                        </button>
                    </div>
                </div>

                <div class="stats-grid" id="departmentsGrid">
                    <!-- Department cards will be loaded here -->
                </div>
            </div>
        </main>
    </div>

    <!-- MODALS -->
    <!-- Add Employee Modal -->
    <div id="addEmployeeModal" class="modal">
        <div class="modal-content">
            <button class="close-modal" onclick="closeModal('addEmployeeModal')">&times;</button>
            <h2 style="margin-bottom: 25px;"><i class="fas fa-user-plus" style="color: #006600;"></i> Add New Employee</h2>
            
            <div class="form-row">
                <div class="form-group">
                    <label>First Name</label>
                    <input type="text" id="empFirstName" placeholder="Enter first name">
                </div>
                <div class="form-group">
                    <label>Last Name</label>
                    <input type="text" id="empLastName" placeholder="Enter last name">
                </div>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label>Email</label>
                    <input type="email" id="empEmail" placeholder="employee@company.com">
                </div>
                <div class="form-group">
                    <label>Phone</label>
                    <input type="tel" id="empPhone" placeholder="03XX-XXXXXXX">
                </div>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label>Department</label>
                    <select id="empDepartment">
                        <option value="">-- Select Department --</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Position</label>
                    <input type="text" id="empPosition" placeholder="e.g., Software Developer">
                </div>
            </div>
            
            <div class="form-row">
                <div class="form-group">
                    <label>Salary (PKR)</label>
                    <input type="number" id="empSalary" placeholder="50000" min="0" step="1000">
                </div>
                <div class="form-group">
                    <label>Hire Date</label>
                    <input type="date" id="empHireDate" value="">
                </div>
            </div>
            
            <div style="display: flex; gap: 15px; margin-top: 25px;">
                <button class="btn btn-primary" onclick="addNewEmployee()" style="flex: 1;">
                    <i class="fas fa-save"></i> Save Employee
                </button>
                <button class="btn btn-primary" onclick="closeModal('addEmployeeModal')" style="flex: 1; background: #777;">
                    <i class="fas fa-times"></i> Cancel
                </button>
            </div>
        </div>
    </div>

    <!-- Add Department Modal -->
    <div id="addDeptModal" class="modal">
        <div class="modal-content">
            <button class="close-modal" onclick="closeModal('addDeptModal')">&times;</button>
            <h2 style="margin-bottom: 25px;"><i class="fas fa-plus-circle" style="color: #006600;"></i> Add New Department</h2>
            
            <div class="form-group">
                <label>Department Name</label>
                <input type="text" id="deptName" placeholder="e.g., Information Technology">
            </div>
            
            <div class="form-group">
                <label>Location</label>
                <input type="text" id="deptLocation" placeholder="e.g., 2nd Floor, Building A">
            </div>
            
            <div class="form-group">
                <label>Budget (PKR)</label>
                <input type="number" id="deptBudget" placeholder="1000000" min="0" step="10000">
            </div>
            
            <div style="display: flex; gap: 15px; margin-top: 25px;">
                <button class="btn btn-primary" onclick="addNewDepartment()" style="flex: 1;">
                    <i class="fas fa-save"></i> Save Department
                </button>
                <button class="btn btn-primary" onclick="closeModal('addDeptModal')" style="flex: 1; background: #777;">
                    <i class="fas fa-times"></i> Cancel
                </button>
            </div>
        </div>
    </div>

    <!-- Payroll Detail Modal -->
    <div id="payrollDetailModal" class="modal">
        <div class="modal-content">
            <button class="close-modal" onclick="closeModal('payrollDetailModal')">&times;</button>
            <h2 style="margin-bottom: 25px;"><i class="fas fa-file-invoice" style="color: #006600;"></i> Payroll Details</h2>
            
            <div id="payrollDetails">
                <!-- Payroll details will be loaded here -->
            </div>
        </div>
    </div>

    <!-- NOTIFICATION AREA -->
    <div id="notificationArea"></div>

    <!-- Chart.js -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    
    <!-- JAVASCRIPT -->
    <script>
        // ===== APPLICATION DATA =====
        let employees = JSON.parse(localStorage.getItem('payrollEmployees')) || [
            {id: 1, name: "Aqleem Tunio", email: "aqleem@company.com", phone: "0312-3456789", 
             dept: "IT", position: "Software Developer", salary: 200000, status: "Active"},
            {id: 2, name: "Farooque Ahmed", email: "farooque@company.com", phone: "0333-9876543",
             dept: "Sales", position: "Sales Executive", salary: 150000, status: "Active"},
            {id: 3, name: "Mubashir Ahmed", email: "mubashir@company.com", phone: "0300-1234567",
             dept: "HR", position: "HR Manager", salary: 180000, status: "Active"},
            {id: 4, name: "Sarah Ali", email: "sarah@company.com", phone: "0321-9876543",
             dept: "Finance", position: "Accountant", salary: 160000, status: "On Leave"}
        ];

        let departments = JSON.parse(localStorage.getItem('payrollDepartments')) || [
            {id: 1, name: "IT", location: "2nd Floor", budget: 5000000, employees: 1},
            {id: 2, name: "Sales", location: "Ground Floor", budget: 3000000, employees: 1},
            {id: 3, name: "HR", location: "1st Floor", budget: 2000000, employees: 1},
            {id: 4, name: "Finance", location: "1st Floor", budget: 4000000, employees: 1}
        ];

        let payrolls = JSON.parse(localStorage.getItem('payrollData')) || [
            {id: 1, empId: 1, empName: "Aqleem Ahmed", month: "Jan 2024", 
             basic: 200000, allowances: 30000, deductions: 25000, net: 205000, status: "Paid"},
            {id: 2, empId: 2, empName: "Farooque Ahmed", month: "Jan 2024",
             basic: 150000, allowances: 22500, deductions: 18000, net: 154500, status: "Paid"},
            {id: 3, empId: 3, empName: "Mubashir Ahmed", month: "Jan 2024",
             basic: 180000, allowances: 27000, deductions: 21600, net: 185400, status: "Pending"}
        ];

        let attendance = JSON.parse(localStorage.getItem('attendanceData')) || [
            {id: 1, date: "2024-01-15", empId: 1, empName: "Aqleem Ahmed", dept: "IT",
             status: "Present", checkIn: "09:00", checkOut: "17:00"},
            {id: 2, date: "2024-01-15", empId: 2, empName: "Farooque Ahmed", dept: "Sales",
             status: "Present", checkIn: "09:15", checkOut: "17:30"},
            {id: 3, date: "2024-01-15", empId: 3, empName: "Mubashir Ahmed", dept: "HR",
             status: "Half-day", checkIn: "09:00", checkOut: "13:00"},
            {id: 4, date: "2024-01-15", empId: 4, empName: "Sarah Ali", dept: "Finance",
             status: "Leave", checkIn: "", checkOut: ""}
        ];

        // ===== UTILITY FUNCTIONS =====
        function saveToLocalStorage() {
            localStorage.setItem('payrollEmployees', JSON.stringify(employees));
            localStorage.setItem('payrollDepartments', JSON.stringify(departments));
            localStorage.setItem('payrollData', JSON.stringify(payrolls));
            localStorage.setItem('attendanceData', JSON.stringify(attendance));
        }

        function formatPKR(amount) {
            return amount.toLocaleString('en-PK') + ' PKR';
        }

        function showNotification(message, type = 'success') {
            const notificationArea = document.getElementById('notificationArea');
            const notification = document.createElement('div');
            notification.className = `notification ${type}`;
            notification.innerHTML = `
                <i class="fas fa-${type === 'success' ? 'check-circle' : type === 'error' ? 'exclamation-circle' : 'info-circle'}"></i>
                <span>${message}</span>
            `;
            
            notificationArea.appendChild(notification);
            
            setTimeout(() => {
                notification.remove();
            }, 3000);
        }

        function showModal(modalId) {
            document.getElementById(modalId).style.display = 'flex';
        }

        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
        }

        function showTab(tabId) {
            // Hide all tabs
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Remove active class from all nav links
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active');
            });
            
            // Show selected tab
            document.getElementById(tabId).classList.add('active');
            
            // Add active class to clicked nav link
            document.querySelector(`a[href="#${tabId}"]`).classList.add('active');
            
            // Refresh data for the tab
            if (tabId === 'dashboard') {
                updateDashboard();
                renderCharts();
            } else if (tabId === 'employees') {
                loadEmployeeTable();
            } else if (tabId === 'payroll') {
                loadPayrollTable();
            } else if (tabId === 'attendance') {
                loadAttendanceTable();
            } else if (tabId === 'departments') {
                loadDepartments();
            }
        }

        // ===== DASHBOARD FUNCTIONS =====
        function updateDashboard() {
            document.getElementById('totalEmployees').textContent = employees.length;
            
            const totalSalary = employees.reduce((sum, emp) => sum + emp.salary, 0);
            document.getElementById('monthlyPayroll').textContent = totalSalary.toLocaleString('en-PK');
            
            document.getElementById('totalDepartments').textContent = departments.length;
            
            const today = new Date().toISOString().split('T')[0];
            const todayAtt = attendance.filter(a => a.date === today);
            const presentCount = todayAtt.filter(a => a.status === 'Present').length;
            document.getElementById('todayAttendance').textContent = `${presentCount}/${employees.length}`;
        }

        function renderCharts() {
            // Department Distribution Chart
            const deptCtx = document.getElementById('deptChart').getContext('2d');
            const deptNames = departments.map(d => d.name);
            const deptCounts = departments.map(d => d.employees || 0);
            
            new Chart(deptCtx, {
                type: 'doughnut',
                data: {
                    labels: deptNames,
                    datasets: [{
                        data: deptCounts,
                        backgroundColor: ['#006600', '#C0A062', '#2C3E50', '#666666'],
                        borderWidth: 2,
                        borderColor: '#fff'
                    }]
                },
                options: {
                    responsive: true,
                    plugins: {
                        legend: { position: 'bottom' },
                        tooltip: { callbacks: { label: ctx => `${ctx.label}: ${ctx.raw} employees` } }
                    }
                }
            });

            // Payroll Trend Chart
            const payrollCtx = document.getElementById('payrollChart').getContext('2d');
            const months = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'];
            const payrollTrend = months.map((_, i) => {
                const base = 1500000;
                const variation = Math.random() * 200000;
                return Math.round(base + variation);
            });
            
            new Chart(payrollCtx, {
                type: 'line',
                data: {
                    labels: months,
                    datasets: [{
                        label: 'Monthly Payroll (PKR)',
                        data: payrollTrend,
                        borderColor: '#006600',
                        backgroundColor: 'rgba(0, 102, 0, 0.1)',
                        borderWidth: 3,
                        fill: true,
                        tension: 0.4
                    }]
                },
                options: {
                    responsive: true,
                    plugins: {
                        legend: { display: false }
                    },
                    scales: {
                        y: {
                            beginAtZero: false,
                            ticks: { 
                                callback: value => 'PKR ' + value.toLocaleString('en-PK')
                            }
                        }
                    }
                }
            });
        }

        // ===== EMPLOYEE MANAGEMENT =====
        function loadEmployeeTable() {
            const tbody = document.getElementById('employeeTableBody');
            tbody.innerHTML = '';
            
            employees.forEach(emp => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${emp.id}</td>
                    <td>
                        <div style="font-weight: 600;">${emp.name}</div>
                        <div style="font-size: 0.9rem; color: #666;">${emp.email}</div>
                    </td>
                    <td><span class="badge badge-pk">${emp.dept}</span></td>
                    <td>${emp.position}</td>
                    <td><span class="currency-pkr">${formatPKR(emp.salary)}</span></td>
                    <td>
                        <span class="badge ${emp.status === 'Active' ? 'badge-success' : 
                                           emp.status === 'On Leave' ? 'badge-warning' : 'badge-danger'}">
                            ${emp.status}
                        </span>
                    </td>
                    <td>
                        <div class="action-buttons">
                            <button class="action-btn edit-btn" onclick="editEmployee(${emp.id})">
                                <i class="fas fa-edit"></i>
                            </button>
                            <button class="action-btn delete-btn" onclick="deleteEmployee(${emp.id})">
                                <i class="fas fa-trash"></i>
                            </button>
                        </div>
                    </td>
                `;
                tbody.appendChild(row);
            });
            
            // Load dropdowns
            const empDeptSelect = document.getElementById('empDepartment');
            empDeptSelect.innerHTML = '<option value="">-- Select Department --</option>';
            departments.forEach(dept => {
                empDeptSelect.innerHTML += `<option value="${dept.name}">${dept.name}</option>`;
            });
            
            const attendanceEmpSelect = document.getElementById('attendanceEmployee');
            attendanceEmpSelect.innerHTML = '<option value="">-- Select Employee --</option>';
            employees.forEach(emp => {
                attendanceEmpSelect.innerHTML += `<option value="${emp.id}">${emp.name}</option>`;
            });
            
            const payrollEmpSelect = document.getElementById('payrollEmployee');
            payrollEmpSelect.innerHTML = '<option value="">-- Select Employee --</option>';
            employees.forEach(emp => {
                payrollEmpSelect.innerHTML += `<option value="${emp.id}">${emp.name} (${emp.dept})</option>`;
            });
        }

        function filterEmployeeTable() {
            const search = document.getElementById('searchEmployee').value.toLowerCase();
            const rows = document.querySelectorAll('#employeeTableBody tr');
            
            rows.forEach(row => {
                const text = row.textContent.toLowerCase();
                row.style.display = text.includes(search) ? '' : 'none';
            });
        }

        function addNewEmployee() {
            const firstName = document.getElementById('empFirstName').value.trim();
            const lastName = document.getElementById('empLastName').value.trim();
            const email = document.getElementById('empEmail').value.trim();
            const phone = document.getElementById('empPhone').value.trim();
            const dept = document.getElementById('empDepartment').value;
            const position = document.getElementById('empPosition').value.trim();
            const salary = parseFloat(document.getElementById('empSalary').value);
            const hireDate = document.getElementById('empHireDate').value;
            
            if (!firstName || !lastName || !email || !dept || !position || !salary) {
                showNotification('Please fill all required fields', 'error');
                return;
            }
            
            const newId = employees.length > 0 ? Math.max(...employees.map(e => e.id)) + 1 : 1;
            const newEmployee = {
                id: newId,
                name: `${firstName} ${lastName}`,
                email: email,
                phone: phone,
                dept: dept,
                position: position,
                salary: salary,
                status: 'Active',
                hireDate: hireDate || new Date().toISOString().split('T')[0]
            };
            
            employees.push(newEmployee);
            saveToLocalStorage();
            loadEmployeeTable();
            updateDashboard();
            
            // Update department employee count
            const deptIndex = departments.findIndex(d => d.name === dept);
            if (deptIndex !== -1) {
                departments[deptIndex].employees = (departments[deptIndex].employees || 0) + 1;
                loadDepartments();
            }
            
            closeModal('addEmployeeModal');
            showNotification('Employee added successfully!');
            
            // Clear form
            ['empFirstName', 'empLastName', 'empEmail', 'empPhone', 'empPosition', 'empSalary', 'empHireDate'].forEach(id => {
                document.getElementById(id).value = '';
            });
        }

        function editEmployee(empId) {
            const emp = employees.find(e => e.id === empId);
            if (emp) {
                showNotification(`Edit mode for ${emp.name}. In a real app, this would open an edit form.`, 'info');
            }
        }

        function deleteEmployee(empId) {
            if (confirm('Are you sure you want to delete this employee?')) {
                const empIndex = employees.findIndex(e => e.id === empId);
                if (empIndex !== -1) {
                    const emp = employees[empIndex];
                    const empName = emp.name;
                    
                    // Update department employee count
                    const deptIndex = departments.findIndex(d => d.name === emp.dept);
                    if (deptIndex !== -1 && departments[deptIndex].employees > 0) {
                        departments[deptIndex].employees -= 1;
                    }
                    
                    employees.splice(empIndex, 1);
                    saveToLocalStorage();
                    loadEmployeeTable();
                    updateDashboard();
                    loadDepartments();
                    showNotification(`Employee ${empName} deleted successfully!`);
                }
            }
        }

        // ===== PAYROLL FUNCTIONS =====
        function loadPayrollTable() {
            const tbody = document.getElementById('payrollTableBody');
            tbody.innerHTML = '';
            
            payrolls.forEach(payroll => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>#${payroll.id}</td>
                    <td>${payroll.empName}</td>
                    <td>${payroll.month}</td>
                    <td>${formatPKR(payroll.basic)}</td>
                    <td>${formatPKR(payroll.allowances)}</td>
                    <td>${formatPKR(payroll.deductions)}</td>
                    <td><strong>${formatPKR(payroll.net)}</strong></td>
                    <td>
                        <span class="badge ${payroll.status === 'Paid' ? 'badge-success' : 'badge-warning'}">
                            ${payroll.status}
                        </span>
                    </td>
                    <td>
                        <button class="action-btn view-btn" onclick="viewPayrollDetails(${payroll.id})">
                            <i class="fas fa-eye"></i>
                        </button>
                        ${payroll.status === 'Pending' ? 
                            `<button class="action-btn edit-btn" onclick="markPayrollPaid(${payroll.id})">
                                <i class="fas fa-check"></i>
                            </button>` : ''
                        }
                    </td>
                `;
                tbody.appendChild(row);
            });
        }

        function calculatePayroll() {
            const empId = parseInt(document.getElementById('payrollEmployee').value);
            const month = document.getElementById('payrollMonth').value;
            const year = document.getElementById('payrollYear').value;
            
            if (!empId) {
                showNotification('Please select an employee', 'error');
                return;
            }
            
            const employee = employees.find(e => e.id === empId);
            if (!employee) {
                showNotification('Employee not found', 'error');
                return;
            }
            
            const monthNames = ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            const monthName = monthNames[parseInt(month) - 1];
            
            const basic = employee.salary;
            const allowances = basic * 0.15; // 15% allowances
            const deductions = basic * 0.12; // 12% deductions (PF, tax, etc.)
            const net = basic + allowances - deductions;
            
            const newId = payrolls.length > 0 ? Math.max(...payrolls.map(p => p.id)) + 1 : 1;
            const newPayroll = {
                id: newId,
                empId: empId,
                empName: employee.name,
                month: `${monthName} ${year}`,
                basic: basic,
                allowances: allowances,
                deductions: deductions,
                net: net,
                status: 'Pending'
            };
            
            payrolls.push(newPayroll);
            saveToLocalStorage();
            loadPayrollTable();
            showNotification(`Payroll calculated for ${employee.name}: ${formatPKR(net)}`);
        }

        function markPayrollPaid(payrollId) {
            const payrollIndex = payrolls.findIndex(p => p.id === payrollId);
            if (payrollIndex !== -1) {
                payrolls[payrollIndex].status = 'Paid';
                saveToLocalStorage();
                loadPayrollTable();
                showNotification('Payroll marked as paid!');
            }
        }

        function viewPayrollDetails(payrollId) {
            const payroll = payrolls.find(p => p.id === payrollId);
            if (payroll) {
                document.getElementById('payrollDetails').innerHTML = `
                    <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; margin-bottom: 20px; border-left: 4px solid #006600;">
                        <h3 style="color: #006600; margin-bottom: 15px;">${payroll.empName} - ${payroll.month}</h3>
                        
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-bottom: 20px;">
                            <div style="border-right: 2px solid #eee; padding-right: 15px;">
                                <p style="color: #666; margin-bottom: 5px; font-size: 0.9rem;">Basic Salary</p>
                                <h3 style="color: #2C3E50;">${formatPKR(payroll.basic)}</h3>
                            </div>
                            <div>
                                <p style="color: #666; margin-bottom: 5px; font-size: 0.9rem;">Allowances</p>
                                <h3 style="color: #006600;">${formatPKR(payroll.allowances)}</h3>
                            </div>
                            <div style="border-right: 2px solid #eee; padding-right: 15px;">
                                <p style="color: #666; margin-bottom: 5px; font-size: 0.9rem;">Deductions</p>
                                <h3 style="color: #777;">${formatPKR(payroll.deductions)}</h3>
                            </div>
                            <div>
                                <p style="color: #666; margin-bottom: 5px; font-size: 0.9rem;">Net Salary</p>
                                <h3 style="color: #006600;">${formatPKR(payroll.net)}</h3>
                            </div>
                        </div>
                        
                        <div style="background: white; padding: 15px; border-radius: 8px; border-left: 4px solid #C0A062;">
                            <p style="margin-bottom: 5px;"><strong>Status:</strong> 
                                <span class="badge ${payroll.status === 'Paid' ? 'badge-success' : 'badge-warning'}">
                                    ${payroll.status}
                                </span>
                            </p>
                            <p style="margin-bottom: 5px;"><strong>Payment Method:</strong> Bank Transfer</p>
                            <p><strong>Processed Date:</strong> ${new Date().toLocaleDateString()}</p>
                            <p><strong>🇵🇰 Pakistan Rupees (PKR)</strong></p>
                        </div>
                    </div>
                    
                    <button class="btn btn-primary" onclick="printPayroll(${payrollId})" style="width: 100%;">
                        <i class="fas fa-print"></i> Print Salary Slip
                    </button>
                `;
                
                showModal('payrollDetailModal');
            }
        }

        function printPayroll(payrollId) {
            showNotification('Printing salary slip...', 'info');
        }

        // ===== ATTENDANCE FUNCTIONS =====
        function loadAttendanceTable() {
            const tbody = document.getElementById('attendanceTableBody');
            tbody.innerHTML = '';
            
            // Set today's date in date picker
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('attendanceDate').value = today;
            
            attendance.forEach(record => {
                const row = document.createElement('tr');
                const date = new Date(record.date);
                const formattedDate = date.toLocaleDateString('en-PK', { 
                    weekday: 'short', 
                    month: 'short', 
                    day: 'numeric' 
                });
                
                row.innerHTML = `
                    <td>${formattedDate}</td>
                    <td>${record.empName}</td>
                    <td><span class="badge badge-pk">${record.dept}</span></td>
                    <td>
                        <span class="badge ${record.status === 'Present' ? 'badge-success' : 
                                           record.status === 'Absent' ? 'badge-danger' : 
                                           record.status === 'Half-day' ? 'badge-warning' : 'badge-warning'}">
                            ${record.status}
                        </span>
                    </td>
                    <td>${record.checkIn || '-'}</td>
                    <td>${record.checkOut || '-'}</td>
                    <td>
                        <button class="action-btn delete-btn" onclick="deleteAttendance(${record.id})">
                            <i class="fas fa-trash"></i>
                        </button>
                    </td>
                `;
                tbody.appendChild(row);
            });
        }

        function markAttendance() {
            const empId = parseInt(document.getElementById('attendanceEmployee').value);
            const date = document.getElementById('attendanceDate').value;
            const status = document.getElementById('attendanceStatus').value;
            
            if (!empId) {
                showNotification('Please select an employee', 'error');
                return;
            }
            
            const employee = employees.find(e => e.id === empId);
            if (!employee) {
                showNotification('Employee not found', 'error');
                return;
            }
            
            // Generate check-in/out times based on status
            let checkIn = '', checkOut = '';
            if (status === 'Present') {
                checkIn = '09:' + (Math.floor(Math.random() * 15)).toString().padStart(2, '0');
                checkOut = '17:' + (Math.floor(Math.random() * 30)).toString().padStart(2, '0');
            } else if (status === 'Half-day') {
                checkIn = '09:00';
                checkOut = '13:00';
            }
            
            const newId = attendance.length > 0 ? Math.max(...attendance.map(a => a.id)) + 1 : 1;
            const newAttendance = {
                id: newId,
                date: date,
                empId: empId,
                empName: employee.name,
                dept: employee.dept,
                status: status,
                checkIn: checkIn,
                checkOut: checkOut
            };
            
            attendance.push(newAttendance);
            saveToLocalStorage();
            loadAttendanceTable();
            updateDashboard();
            
            const statusIcon = status === 'Present' ? '✅' : status === 'Absent' ? '❌' : status === 'Half-day' ? '🕐' : '🏖️';
            showNotification(`${statusIcon} Attendance marked for ${employee.name}`);
        }

        function deleteAttendance(attendanceId) {
            if (confirm('Are you sure you want to delete this attendance record?')) {
                const attIndex = attendance.findIndex(a => a.id === attendanceId);
                if (attIndex !== -1) {
                    attendance.splice(attIndex, 1);
                    saveToLocalStorage();
                    loadAttendanceTable();
                    showNotification('Attendance record deleted!');
                }
            }
        }

        // ===== DEPARTMENT FUNCTIONS =====
        function loadDepartments() {
            const deptGrid = document.getElementById('departmentsGrid');
            deptGrid.innerHTML = '';
            
            departments.forEach(dept => {
                const card = document.createElement('div');
                card.className = 'stat-card';
                card.style.cursor = 'pointer';
                card.onclick = () => showDeptDetails(dept.id);
                
                const colors = ['#006600', '#C0A062', '#2C3E50', '#666666'];
                const color = colors[dept.id % colors.length];
                
                card.innerHTML = `
                    <div class="stat-info">
                        <h3>${dept.name}</h3>
                        <h2>${dept.employees || 0}</h2>
                        <p style="color: #666; font-size: 0.9rem;">${dept.location}</p>
                        <p style="color: #666; font-size: 0.9rem;">Budget: ${formatPKR(dept.budget)}</p>
                    </div>
                    <div class="stat-icon" style="background: ${color};">
                        <i class="fas fa-building"></i>
                    </div>
                `;
                
                deptGrid.appendChild(card);
            });
        }

        function addNewDepartment() {
            const name = document.getElementById('deptName').value.trim();
            const location = document.getElementById('deptLocation').value.trim();
            const budget = parseFloat(document.getElementById('deptBudget').value);
            
            if (!name || !location || !budget) {
                showNotification('Please fill all fields', 'error');
                return;
            }
            
            const newId = departments.length > 0 ? Math.max(...departments.map(d => d.id)) + 1 : 1;
            const newDept = {
                id: newId,
                name: name,
                location: location,
                budget: budget,
                employees: 0
            };
            
            departments.push(newDept);
            saveToLocalStorage();
            loadDepartments();
            updateDashboard();
            
            closeModal('addDeptModal');
            showNotification(`Department "${name}" added successfully!`);
            
            // Clear form
            document.getElementById('deptName').value = '';
            document.getElementById('deptLocation').value = '';
            document.getElementById('deptBudget').value = '';
        }

        function showDeptDetails(deptId) {
            const dept = departments.find(d => d.id === deptId);
            if (dept) {
                const deptEmployees = employees.filter(e => e.dept === dept.name);
                
                document.getElementById('payrollDetails').innerHTML = `
                    <div style="background: #f8f9fa; padding: 20px; border-radius: 10px; border-left: 4px solid #C0A062;">
                        <h3 style="color: #C0A062; margin-bottom: 15px;">${dept.name} Department</h3>
                        
                        <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin-bottom: 20px;">
                            <div style="border-right: 2px solid #eee; padding-right: 15px;">
                                <p style="color: #666; margin-bottom: 5px; font-size: 0.9rem;">Location</p>
                                <h4 style="color: #2C3E50;">${dept.location}</h4>
                            </div>
                            <div>
                                <p style="color: #666; margin-bottom: 5px; font-size: 0.9rem;">Budget</p>
                                <h4 style="color: #006600;">${formatPKR(dept.budget)}</h4>
                            </div>
                            <div style="border-right: 2px solid #eee; padding-right: 15px;">
                                <p style="color: #666; margin-bottom: 5px; font-size: 0.9rem;">Total Employees</p>
                                <h4 style="color: #006600;">${deptEmployees.length}</h4>
                            </div>
                            <div>
                                <p style="color: #666; margin-bottom: 5px; font-size: 0.9rem;">Avg. Salary</p>
                                <h4 style="color: #C0A062;">
                                    ${deptEmployees.length > 0 ? 
                                        formatPKR(Math.round(deptEmployees.reduce((sum, e) => sum + e.salary, 0) / deptEmployees.length)) : 
                                        'PKR 0'}
                                </h4>
                            </div>
                        </div>
                        
                        <h4 style="margin-bottom: 15px; color: #555;">Department Employees</h4>
                        <div style="max-height: 200px; overflow-y: auto;">
                            ${deptEmployees.map(emp => `
                                <div style="display: flex; justify-content: space-between; align-items: center; 
                                            padding: 10px; background: white; margin-bottom: 8px; border-radius: 8px; border-left: 4px solid #006600;">
                                    <div>
                                        <strong>${emp.name}</strong>
                                        <div style="font-size: 0.9rem; color: #666;">${emp.position}</div>
                                    </div>
                                    <div style="font-weight: 600; color: #006600;">
                                        ${formatPKR(emp.salary)}
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                `;
                
                showModal('payrollDetailModal');
            }
        }

        // ===== INITIALIZATION =====
        window.onload = function() {
            // Load initial data
            loadEmployeeTable();
            updateDashboard();
            renderCharts();
            loadAttendanceTable();
            loadDepartments();
            loadPayrollTable();
            
            // Set today's date in forms
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('empHireDate').value = today;
            document.getElementById('attendanceDate').value = today;
            
            // Close modals when clicking outside
            window.onclick = function(event) {
                document.querySelectorAll('.modal').forEach(modal => {
                    if (event.target === modal) {
                        modal.style.display = 'none';
                    }
                });
            };
        };

        // Export data function
        function exportData() {
            const data = {
                employees: employees,
                departments: departments,
                payrolls: payrolls,
                attendance: attendance,
                exported: new Date().toISOString(),
                currency: "PKR"
            };
            
            const dataStr = JSON.stringify(data, null, 2);
            const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
            const exportFileDefaultName = 'payroll-data-pakistan-' + new Date().toISOString().split('T')[0] + '.json';
            
            const linkElement = document.createElement('a');
            linkElement.setAttribute('href', dataUri);
            linkElement.setAttribute('download', exportFileDefaultName);
            linkElement.click();
            
            showNotification('Data exported successfully!');
        }
        
        // Add export button to dashboard
        document.addEventListener('DOMContentLoaded', function() {
            const quickActions = document.querySelector('#dashboard .btn-group');
            if (quickActions) {
                const exportBtn = document.createElement('button');
                exportBtn.className = 'btn btn-primary';
                exportBtn.innerHTML = '<i class="fas fa-download"></i> Export Data';
                exportBtn.onclick = exportData;
                quickActions.appendChild(exportBtn);
            }
        });
    </script>
</body>
</html>
