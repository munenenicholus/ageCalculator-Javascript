# Greetings Form

This is a simple web application that allows you to enter your birth date and displays a greeting message based on your age. The application is built using HTML, CSS (Bootstrap), and JavaScript.

## How to Use

1. Open the `index.html` file in your web browser.
2. You will see a card with a form asking you to enter your date of birth.
3. Click on the input field and select your birth date from the date picker.
4. After selecting your birth date, click on the "Submit" button.
5. The application will calculate your age based on the provided birth date and display a personalized greeting message below the form.

## Dependencies

The application uses the following libraries to enhance the user interface:

- Bootstrap CSS: The application uses Bootstrap CSS to style the form and card layout. The CSS is included via the following link:
  ```html
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
  ```

- Bootstrap JS: The Bootstrap JavaScript library is used to handle certain components like buttons. It is included via the following script tag:
  ```html
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
  ```

## Custom JavaScript

The core functionality of the application is implemented in JavaScript. When you submit the form, the JavaScript code calculates your age and generates an appropriate greeting message based on your birth date. The code snippet is provided below:

```html
<script>
  document.getElementById('greetingsForm').addEventListener('submit', function(event) {
    event.preventDefault(); // Prevent form submission to avoid page reload
    var birthdate = new Date(document.getElementById('birthdate').value);
    var today = new Date();
    var age = today.getFullYear() - birthdate.getFullYear();

    // Check if the birthday has already occurred this year
    if (today.getMonth() < birthdate.getMonth() || (today.getMonth() === birthdate.getMonth() && today.getDate() < birthdate.getDate())) {
      age--;
    }

    var greetingMessage;
    if (age < 0) {
      greetingMessage = "Oops! You seem to be from the future.";
    } else if (age === 0) {
      greetingMessage = "Happy Birthday! Congratulations on your first birthday!";
    } else {
      greetingMessage = "Happy " + age + "th Birthday!";
    }

    document.getElementById('greetingMessage').innerText = greetingMessage;
  });
</script>
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Feel free to use, modify, and distribute this project according to the terms of the MIT License.

## Author

This application was created by [Your Name].

For any questions or inquiries, please contact emoredesigns39@gmail.com.