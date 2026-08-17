1. #!/bin/bash
# Prompt user for input
echo -n "Enter first number: "
read num1
echo -n "Enter second number: "
read num2
# Perform calculations
sum=$((num1 + num2))
diff=$((num1 - num2))
prod=$((num1 * num2))
# Display results
echo "Results:"
echo "$num1 + $num2 = $sum"
echo "$num1 - $num2 = $diff"
echo "$num1 × $num2 = $prod"
# Handle division by zero
if [ "$num2" -eq 0 ]; then
    echo "$num1 ÷ $num2 = Error (division by zero)"
else
    div=$((num1 / num2))
    echo "$num1 ÷ $num2 = $div"
fi
this script allows for 2 numbers to be devided, added and subracticted from each other and it outputs this with the formula.

2. #!/bin/bash
# Create directory
dir_name="bash_demo"
file_name="demo.txt"
mkdir -p "$dir_name"
echo "Directory '$dir_name' created."
# Navigate into directory
cd "$dir_name" || exit
# Create file and write content with current date
current_date=$(date +%Y-%m-%d)
echo "This file was created by a Bash script on $current_date" > "$file_name"
echo "File '$file_name' created."
# Display file contents
echo "File contents:"
cat "$file_name"
this script creates a directory 
