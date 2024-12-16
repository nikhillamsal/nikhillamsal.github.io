<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Email Validation</title>
  </head>
  <body>
    <form id="emailForm">
      <label for="email">Email:</label>
      <input type="text" id="email" name="email" />
      <button type="submit">Submit</button>
      <p id="error-message" style="color: red"></p>
    </form>

    <script>
      document
        .getElementById("emailForm")
        .addEventListener("submit", function (event) {
          event.preventDefault();

          const emailInput = document.getElementById("email");
          const errorMessage = document.getElementById("error-message");
          const email = emailInput.value;

          if (validateEmail(email)) {
            errorMessage.textContent = "";
            console.log("Valid email:", email);
          } else {
            errorMessage.textContent = "Please enter a valid email address.";
          }
        });

      function validateEmail(email) {
        const regex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return regex.test(email);
      }
    </script>
  </body>
</html>
