//Create an array with the values (1, 2, 3, 4, 5, 6, 7) and shuffle it.
          package test;
          import java.util.ArrayList;
          import java.util.Collections;
          import java.util.List;
          import java.util.Arrays;
          public class Array 
    { 
          public static void main(String[] args) 
      {
          Integer[] array = {1, 2, 3, 4, 5, 6, 7};
          List<Integer> list = new ArrayList<>(Arrays.asList(array));
          Collections.shuffle(list);
          Integer[] shuffledArray = list.toArray(new Integer[0]);
          System.out.println("Shuffled Array: " + Arrays.toString(shuffledArray));
      }
    }

//Enter a Roman Number as input and convert it to an integer.
      package test;
      import java.util.HashMap;

      public class RomanNumberToInteger 
  {
      public static void main(String[] args) 
    {
      String romanNumeral = "I"; 
      int result = romanToInt(romanNumeral);
      System.out.println("Roman numeral " + romanNumeral + " is equivalent to " + result);
    }
      public static int romanToInt(String s) 
    {
        HashMap<Character, Integer> romanValues = new HashMap<>();
        romanValues.put('I', 1);
        romanValues.put('V', 5);
        romanValues.put('X', 10);
        romanValues.put('L', 50);
        romanValues.put('C', 100);
        romanValues.put('D', 500);
        romanValues.put('M', 1000);
        int result = 0;
        int prevValue = 0;
        for (int i = s.length() - 1; i >= 0; i--) 
      {
        char c = s.charAt(i);
        int value = romanValues.get(c);
        if (value < prevValue) 
        {
            result -= value;
        } else 
        {
            result += value;
        }
        prevValue = value;
      }
    return result;
  }
}

//Check if the input is pangram or not.
        package test;
        import java.util.HashSet;
        import java.util.Scanner;

        public class PangramOrNot 
{
	      public static void main(String[] args) 
    {
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter a sentence: ");
        String input = scan.nextLine();
        if (isPangram(input)) 
        {
            System.out.println("The input is a pangram.");
        } 
        else 
        {
            System.out.println("The input is not a pangram.");
        }
   }
    
        public static boolean isPangram(String input) 
    {
        input = input.toLowerCase();
        HashSet<Character> alphabetSet = new HashSet<>();
        for (char c : input.toCharArray()) 
        {
            if (c >= 'a' && c <= 'z') 
            {
                alphabetSet.add(c);
            }
        }
        return alphabetSet.size() == 26;
    }
}

//Take a sentence as an input and reverse every word in that sentence.
          function reverseWordsInSentence(sentence) 
  {
          const words = sentence.split(' ');
          const reversedWords = words.map(word => 
      {
          return word.split('').reverse().join('');
      });
          const reversedSentence = reversedWords.join(' ');
          return reversedSentence;
  }
          const inputSentence = "Manoj Kumar Reddy";
          const reversedSentence = reverseWordsInSentence(inputSentence);
          console.log(reversedSentence);

  //Perform sorting of an array in descending order.
            const arr = [5, 2, 9, 1, 5, 6];
            arr.sort(function(a, b) 
          {
            return b - a;
          });
            console.log(arr);

  //Create a basic calculator using HTML, CSS, and JavaScript with the functionality of add,
subtract, multiply and divide.
//HTML
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
    <div class="calculator">
        <input type="text" id="display" readonly>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="appendToDisplay('7')">7</button>
            <button onclick="appendToDisplay('8')">8</button>
            <button onclick="appendToDisplay('9')">9</button>
            <button onclick="appendToDisplay('+')">+</button>
            <button onclick="appendToDisplay('4')">4</button>
            <button onclick="appendToDisplay('5')">5</button>
            <button onclick="appendToDisplay('6')">6</button>
            <button onclick="appendToDisplay('-')">-</button>
            <button onclick="appendToDisplay('1')">1</button>
            <button onclick="appendToDisplay('2')">2</button>
            <button onclick="appendToDisplay('3')">3</button>
            <button onclick="appendToDisplay('')"></button>
            <button onclick="appendToDisplay('0')">0</button>
            <button onclick="appendToDisplay('.')">.</button>
            <button onclick="calculateResult()">=</button>
            <button onclick="appendToDisplay('/')">/</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
//CSS
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.calculator {
    text-align: center;
    background-color: #f0f0f0;
    border: 2px solid #ccc;
    border-radius: 5px;
    padding: 20px;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}

input {
    width: 100%;
    margin-bottom: 10px;
    font-size: 20px;
    padding: 5px;
}

button {
    width: 50px;
    height: 50px;
    font-size: 20px;
    margin: 5px;
}
//JavaScript
let display = document.getElementById("display");
let currentInput = "";
let result = 0;

function appendToDisplay(value) {
    currentInput += value;
    display.value = currentInput;
}

function clearDisplay() {
    currentInput = "";
    display.value = "";
}

function calculateResult() {
    try {
        result = eval(currentInput);
        display.value = result;
        currentInput = result.toString();
    } catch (error) {
        display.value = "Error";
    }
}

//Create a survey form with Fields; First Name, Last Name, Date of Birth, Country
(dropdown), Gender (checkbox), Profession, email, and mobile number. All the input
fields are necessary to submit the form. Create two buttons Submit and Reset. Reset will
reset the form while clicking on submit, first, it will check all the fields and necessary
validations and then a popup will appear displaying all the selected values with labels in
front of it. On closing the popup, the form should reset all the values.

//HTML
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
    <div class="survey-form">
        <h1>Survey Form</h1>
        <form id="surveyForm" onsubmit="return false;">
            <div class="form-group">
                <label for="firstName">First Name:</label>
                <input type="text" id="firstName" required>
            </div>
            <div class="form-group">
                <label for="lastName">Last Name:</label>
                <input type="text" id="lastName" required>
            </div>
            <div class="form-group">
                <label for="dob">Date of Birth:</label>
                <input type="date" id="dob" required>
            </div>
            <div class="form-group">
                <label for="country">Country:</label>
                <select id="country" required>
                    <option value="USA">USA</option>
                    <option value="Canada">Canada</option>
                    <option value="UK">UK</option>
                    <option value="Other">Other</option>
                </select>
            </div>
            <div class="form-group">
                <label>Gender:</label><br>
                <input type="checkbox" id="male" name="gender" value="Male">
                <label for="male">Male</label>
                <input type="checkbox" id="female" name="gender" value="Female">
                <label for="female">Female</label>
                <input type="checkbox" id="other" name="gender" value="Other">
                <label for="other">Other</label>
            </div>
            <div class="form-group">
                <label for="profession">Profession:</label>
                <input type="text" id="profession" required>
            </div>
            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" required>
            </div>
            <div class="form-group">
                <label for="mobile">Mobile Number:</label>
                <input type="tel" id="mobile" required>
            </div>
            <div class="button-group">
                <button onclick="resetForm()">Reset</button>
                <button onclick="submitForm()">Submit</button>
            </div>
        </form>
    </div>
    <div id="popup" class="popup">
        <div class="popup-content">
            <span class="close" onclick="closePopup()">&times;</span>
            <h2>Survey Form Submission</h2>
            <div id="popup-values"></div>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

//CSS
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
}
.survey-form {
    width: 60%;
    margin: 0 auto;
    padding: 20px;
    background-color: #fff;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}
.form-group {
    margin-bottom: 20px;
}
label {
    display: block;
    font-weight: bold;
}
input,
select {
    width: 100%;
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ccc;
}
.checkbox-group {
    display: flex;
    align-items: center;
}
.checkbox-group label {
    margin-right: 10px;
}
.button-group {
    display: flex;
    justify-content: space-between;
}
button {
    background-color: #007BFF;
    color: #fff;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
}
button:hover {
    background-color: #0056b3;
}
.popup {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    z-index: 999;
}
.popup-content {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #fff;
    padding: 20px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}
.close {
    position: absolute;
    top: 0;
    right: 0;
    padding: 10px;
    cursor: pointer;
}
.popup-values {
    margin: 20px 0;
}
.popup-values p {
    margin: 0;
}

//JavaScript
function resetForm() {
    document.getElementById("surveyForm").reset();
}

function submitForm() {
    const firstName = document.getElementById("firstName").value;
    const lastName = document.getElementById("lastName").value;
    const dob = document.getElementById("dob").value;
    const country = document.getElementById("country").value;
    const genderCheckboxes = document.querySelectorAll('input[name="gender"]:checked');
    const genderValues = Array.from(genderCheckboxes).map(checkbox => checkbox.value);
    const profession = document.getElementById("profession").value;
    const email = document.getElementById("email").value;
    const mobile = document.getElementById("mobile").value;

    if (
        firstName === "" ||
        lastName === "" ||
        dob === "" ||
        country === "" ||
        genderValues.length === 0 ||
        profession === "" ||
        email === "" ||
        mobile === ""
    ) {
        alert("Please fill in all required fields.");
        return;
    }
    const popupContent = document.getElementById("popup-values");
    popupContent.innerHTML = `
        <p><strong>First Name:</strong> ${firstName}</p>
        <p><strong>Last Name:</strong> ${lastName}</p>
        <p><strong>Date of Birth:</strong> ${dob}</p>
        <p><strong>Country:</strong> ${country}</p>
        <p><strong>Gender:</strong> ${genderValues.join(", ")}</p>
        <p><strong>Profession:</strong> ${profession}</p>
        <p><strong>Email:</strong> ${email}</p>
        <p><strong>Mobile Number:</strong> ${mobile}</p>
    `;
    const popup = document.getElementById("popup");
    popup.style.display = "block";
}
function closePopup() {
    const popup = document.getElementById("popup");
    popup.style.display =
