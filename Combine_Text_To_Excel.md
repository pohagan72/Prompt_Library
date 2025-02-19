This python script was used to join 4 text files into a single Excel file. The Text files were generated using the Image Narration code but because there was 150,000 images, I broke it into 4 parts.

```python
import streamlit as st  # Import the Streamlit library for creating web apps
import pandas as pd  # Import the Pandas library for data manipulation and analysis
import tempfile  # Import the tempfile module for creating temporary files
import os  # Import the os module for interacting with the operating system (used here for handling temporary files)

def process_text_file(file):
    """
    Processes a single text file to extract image names and their corresponding descriptions.

    Args:
        file: A file-like object (obtained from Streamlit's file uploader) containing the text data.

    Returns:
        A tuple containing two lists:
            - image_names: A list of extracted image names.
            - cleaned_descriptions: A list of corresponding descriptions, cleaned up.
    """
    lines = file.readlines()  # Read all lines from the file into a list
    image_names = []  # Initialize an empty list to store image names
    descriptions = []  # Initialize an empty list to store descriptions
    current_description = ''  # Initialize an empty string to accumulate the current description

    for line in lines:
        line = line.decode('utf-8').strip()  # Decode bytes to string and remove leading/trailing whitespace
        if line.startswith('Processing image:'):
            # If the line starts with 'Processing image:', it indicates a new image entry

            # Extract the image name. Split the string by ':' and take the second part, then strip whitespace
            image_name = line.split(':')[1].strip()

            if current_description:
                # If there's a description accumulated from previous lines,
                # add it to the descriptions list before starting a new image
                descriptions.append(current_description.strip())
                current_description = ''  # Reset current_description for the new image

            image_names.append(image_name)  # Add the extracted image name to the image_names list

        elif line == 'Description:':
            # Skip lines that are exactly "Description:"
            continue

        elif line == '--------------':
            # Skip separator lines
            continue

        else:
            # If the line is not a special marker, it's part of the description
            current_description += line + ' '  # Append the line to the current_description, add a space for separation

    # After processing all lines, check if there's any remaining description
    if current_description:
        descriptions.append(current_description.strip())  # Add the last description (if any)

    # Clean the descriptions by removing any remaining "Description:" prefixes
    cleaned_descriptions = [desc.replace('Description:', '').strip() for desc in descriptions]

    return image_names, cleaned_descriptions  # Return the extracted image names and descriptions


def main():
    """
    Main function to run the Streamlit application.
    """
    st.title("Text File Merger")  # Set the title of the Streamlit web application
    uploaded_files = st.file_uploader("Drag and drop text files", type=['txt'], accept_multiple_files=True)
    # Create a file uploader widget that accepts multiple .txt files

    if st.button("Process and Download"):  # Create a button labeled "Process and Download"
        all_image_names = []  # Initialize a list to store image names from all files
        all_descriptions = []  # Initialize a list to store descriptions from all files

        for file in uploaded_files:
            # Iterate through each uploaded file
            image_names, descriptions = process_text_file(file)  # Process each file using the function
            all_image_names.extend(image_names)  # Add the extracted image names to the combined list
            all_descriptions.extend(descriptions)  # Add the extracted descriptions to the combined list

        # Create a Pandas DataFrame to store the combined data
        df = pd.DataFrame({
            'Image': all_image_names,  # Column named 'Image' containing image names
            'Description': all_descriptions  # Column named 'Description' containing descriptions
        })

        # Create a temporary file to store the Excel output.  'delete=False' is important on Windows
        with tempfile.NamedTemporaryFile(suffix='.xlsx', delete=False) as tmp:
            df.to_excel(tmp.name, index=False)  # Write the DataFrame to an Excel file (without the index)
            with open(tmp.name, 'rb') as f:  # Open the temporary Excel file in binary read mode ('rb')
                st.download_button("Download Excel File", data=f, file_name='output.xlsx')
             # Create a download button.  The user clicks this to download the Excel file.
             # The downloaded file will be named 'output.xlsx'.

if __name__ == "__main__":
    main()  # Run the main function if the script is executed directly
```




