# File Read & Write Challenge 🖋️

def read_and_write_file(input_file, output_file):

    try:
        # Open the input file in read mode
        with open(input_file, 'r') as infile:
            content = infile.read()  # Read the entire content of the file
        # Modify the content (e.g., converting to uppercase)
        modified_content = content.upper()
        # Write the modified content to the output file
        with open(output_file, 'w') as outfile:
            outfile.write(modified_content)
        print(f"File '{input_file}' was successfully read and modified content is saved to '{output_file}'.")
    except FileNotFoundError:
        print(f"Error: The file '{input_file}' was not found.")
    except IOError:
        print(f"Error: An issue occurred while reading or writing the file.")

# Error Handling Lab 🧪

def get_filename_and_process():

    # Ask the user for a filename
    filename = input("Please enter the filename you want to process: ")
    try:
        # Try opening the file to check if it exists and is readable
        with open(filename, 'r') as file:
            content = file.read()
            print(f"Content of the file '{filename}':\n")
            print(content)
            # Ask user for an output filename and process the file
            output_filename = input("\nEnter the output filename to save modified content: ")
            read_and_write_file(filename, output_filename)
    except FileNotFoundError:
        print(f"Error: The file '{filename}' does not exist.")
    except IOError:
        print(f"Error: Could not read the file '{filename}'. Please check permissions.")

# Running the error handling function
get_filename_and_process()
