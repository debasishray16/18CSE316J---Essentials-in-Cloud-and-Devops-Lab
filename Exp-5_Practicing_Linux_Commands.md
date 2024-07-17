# Practicing Linux Commands

## Write a Bash script that prompts the user to enter a command and executes it. Additionally, capture the command output and display it with a timestamp

```bash
#!/bin/bash

# Prompt the user to enter a command
echo "Enter a command:"
read user_command

# Execute the command, capture the output with a timestamp
output=$(eval "$user_command" 2>&1)
timestamp=$(date +"[%Y-%m-%d %H:%M:%S]")

# Display the output with the timestamp
echo "$timestamp Output of '$user_command':"
echo "$output"

```

## Write a script that prompts the user for their age and provides different messages based on whether they are a child, teenager, adult, or senior citizen

```bash
#!/bin/bash

# Function to determine the age group message
get_age_group_message() {
  local age=$1
  if [ "$age" -lt 0 ]; then
    echo "Age cannot be negative. Please enter a valid age."
  elif [ "$age" -le 12 ]; then
    echo "You are a child. Enjoy your childhood!"
  elif [ "$age" -le 19 ]; then
    echo "You are a teenager. These are exciting times!"
  elif [ "$age" -le 64 ]; then
    echo "You are an adult. Embrace your responsibilities!"
  else
    echo "You are a senior citizen. Enjoy your golden years!"
  fi
}

# Prompt the user for their age
echo -n "Please enter your age: "
read age

# Call the function and display the message
message=$(get_age_group_message $age)
echo $message
```

## Create a script that performs basic arithmetic operations (addition, subtraction, multiplication, division) on two user-supplied numbers. Display the results with appropriate formatting

```bash
#!/bin/bash

# Function to perform addition
addition() {
    echo "Result of addition: $((num1 + num2))"
}

# Function to perform subtraction
subtraction() {
    echo "Result of subtraction: $((num1 - num2))"
}

# Function to perform multiplication
multiplication() {
    echo "Result of multiplication: $((num1 * num2))"
}

# Function to perform division
division() {
    if [ $num2 -eq 0 ]; then
        echo "Error: Division by zero is not allowed."
    else
        echo "Result of division: $((num1 / num2))"
    fi
}

# Prompt the user for the first number
read -p "Enter the first number: " num1

# Prompt the user for the second number
read -p "Enter the second number: " num2

# Perform arithmetic operations
addition
subtraction
multiplication
division

```

## Build a script that checks if a user-supplied number is even or odd. Use logical operators to validate the input and provide appropriate feedback

```bash
echo "Enter the number:"
read num

# to check if number is divisible by 2 and get an remainder as 0.

if [ $((num%2)) -eq 0 ]; then
        echo "$num is an even number."
else
        echo "$num is a odd number."
fi

```

## Create a script that searches for a specific pattern within a given text file. Allow the user to input the pattern and the file name. Display the matching lines along with line numbers

```bash
#!/bin/bash

# Function to search for pattern in the given file
search_pattern() {
    local pattern="$1"
    local filename="$2"
    
    # Check if the file exists
    if [ ! -f "$filename" ]; then
        echo "Error: File '$filename' not found."
        return 1
    fi

    # Search for the pattern in the file and display matching lines with line numbers
    grep -n "$pattern" "$filename"
}

# Prompt the user to input the pattern
read -p "Enter the pattern to search for: " pattern

# Prompt the user to input the file name
read -p "Enter the file name to search in: " filename

# Call the function to search for the pattern in the file
search_pattern "$pattern" "$filename"

```

## To calculate the length of the string

```bash
string="your_string_here"
echo -n "$string" | wc -c
```

## To concatenate two strings

```bash
str1="Hello, "
str2="world!"
result="${str1}${str2}"
echo "$result"
```

## To reverse a string

```bash
string="hello, world!"
reversed=$(echo "$string" | rev)
echo "$reversed"
```
