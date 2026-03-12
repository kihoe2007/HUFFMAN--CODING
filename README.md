# Ex 11: Huffman-Coding
# Name:  KISHORE S M
# Reg No: 212224230131
## Aim
To implement Huffman coding to compress the data using Python.

Software Required
Anaconda - Python 3.7

## Algorithm:
# Step 1: Take the input string from the user.
# Step 2: Calculate the frequency of each character in the string.
# Step 3: Build the Huffman Tree using a priority queue based on frequencies. 
# Step 4: Traverse the tree to assign binary codes to characters.
# Step 5: Display the Huffman code for each character.
 
## Program:

``` Python
# Get the input String
# Step 1: Get the input string
input_string = "kishore"  # Example input string


# Create tree nodes
# Step 2: Calculate frequency of each character in the input string
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1



# Main function to implement huffman coding
# Step 3: Create tree nodes
nodes = [[char, freq] for char, freq in frequency.items()]
# Step 4: Main function to implement Huffman coding
while len(nodes) > 1:
    # Sort nodes based on frequency
    nodes = sorted(nodes, key=lambda x: x[1])

    # Pick two smallest nodes
    left = nodes.pop(0)
    right = nodes.pop(0)

    # Create a new node with combined frequency
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)

# The final node is the Huffman tree
huffman_tree = nodes[0]


# Calculate frequency of occurrence
# Step 5: Generate Huffman codes
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)



# Print the characters and its huffmancode
# Step 6: Print the characters and their Huffman codes
print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")





```
## Output:

### Print the characters and its huffmancode
<br>
<br>
<br><img width="497" height="236" alt="image" src="https://github.com/user-attachments/assets/1a0dde72-1143-4983-ab8a-acd99e54894c" />

<br>
<br>
<br>



## Result
Thus the huffman coding was implemented to compress the data using python programming.
