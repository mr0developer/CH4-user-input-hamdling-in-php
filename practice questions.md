### 1. Simple Program Using POST Method

**HTML Form:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Information Form</title>
</head>
<body>
    <h2>Enter Student Information</h2>
    <form action="process_student.php" method="POST">
        <label for="name">Enter Student Name:</label><br>
        <input type="text" name="student_name" required><br><br>
        
        <label for="gr_no">Enter Student G.R #:</label><br>
        <input type="text" name="student_grno" required><br><br>
        
        <label for="class">Enter Class:</label><br>
        <input type="text" name="student_class" required><br><br>
        
        <label for="section">Enter Section:</label><br>
        <input type="text" name="student_section" required><br><br>
        
        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

**PHP (process_student.php):**
```php
<?php
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $name = $_POST['student_name'];
    $gr_no = $_POST['student_grno'];
    $class = $_POST['student_class'];
    $section = $_POST['student_section'];

    echo "<h2>Student Information</h2>";
    echo "Student Name: " . $name . "<br>";
    echo "Student G.R #: " . $gr_no . "<br>";
    echo "Class: " . $class . "<br>";
    echo "Section: " . $section . "<br>";
}
?>
```

---

### 2. Input Your G.R No and Course Name (GET and POST Method)

**HTML Form (for POST):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>POST Method</title>
</head>
<body>
    <h2>Enter G.R No and Course Name (POST)</h2>
    <form action="process_post.php" method="POST">
        <label for="gr_no">Enter G.R No:</label><br>
        <input type="text" name="gr_no" required><br><br>

        <label for="course">Enter Course Name:</label><br>
        <input type="text" name="course_name" required><br><br>

        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

**PHP (process_post.php):**
```php
<?php
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $gr_no = $_POST['gr_no'];
    $course = $_POST['course_name'];

    echo "G.R No: " . $gr_no . "<br>";
    echo "Course Name: " . $course . "<br>";
}
?>
```

**HTML Form (for GET):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GET Method</title>
</head>
<body>
    <h2>Enter G.R No and Course Name (GET)</h2>
    <form action="process_get.php" method="GET">
        <label for="gr_no">Enter G.R No:</label><br>
        <input type="text" name="gr_no" required><br><br>

        <label for="course">Enter Course Name:</label><br>
        <input type="text" name="course_name" required><br><br>

        <input type="submit" value="Submit">
    </form>
</body>
</html>
```

**PHP (process_get.php):**
```php
<?php
if ($_SERVER['REQUEST_METHOD'] == 'GET') {
    $gr_no = $_GET['gr_no'];
    $course = $_GET['course_name'];

    echo "G.R No: " . $gr_no . "<br>";
    echo "Course Name: " . $course . "<br>";
}
?>
```

---

### 3. Simple Form with Submit and Reset Buttons

**HTML Form:**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Form</title>
</head>
<body>
    <h2>Enter G.R No and Name</h2>
    <form action="display_info.php" method="POST">
        <label for="gr_no">Enter G.R No:</label><br>
        <input type="text" name="gr_no" required><br><br>

        <label for="name">Enter Name:</label><br>
        <input type="text" name="name" required><br><br>

        <input type="submit" value="Submit">
        <input type="reset" value="Reset">
    </form>
</body>
</html>
```

**PHP (display_info.php):**
```php
<?php
if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $gr_no = $_POST['gr_no'];
    $name = $_POST['name'];

    echo "<h2>Student Information</h2>";
    echo "G.R No: " . $gr_no . "<br>";
    echo "Name: " . $name . "<br>";
}
?>
```

---

### 4. Sending Roll Number and Name Using Hyperlinks

**HTML (page1.php):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hyperlink Example</title>
</head>
<body>
    <h2>Send Roll Number and Name via Hyperlink</h2>
    <a href="page2.php?roll_no=12345&name=JohnDoe">Click here to send Roll No and Name</a>
</body>
</html>
```

**PHP (page2.php):**
```php
<?php
if (isset($_GET['roll_no']) && isset($_GET['name'])) {
    $roll_no = $_GET['roll_no'];
    $name = $_GET['name'];

    echo "Roll No: " . $roll_no . "<br>";
    echo "Name: " . $name . "<br>";
}
?>
```

---

### 5. Syntax of the `action` and `method` Attributes in the Opening `<form>` Tag

```html
<form action="target_page.php" method="POST">
    <!-- Form contents -->
</form>
```

- **`action`**: Specifies the URL or file where form data will be sent for processing (e.g., `action="process.php"`).
- **`method`**: Specifies the HTTP method to use when sending form data. Common values are:
  - **GET**: `method="GET"`
  - **POST**: `method="POST"`
