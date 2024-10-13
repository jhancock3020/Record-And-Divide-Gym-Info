# Google Sheets Gym Workout Organizer

This Google Sheets script helps organize your gym workouts by separating exercises into different sheets based on their category: Legs, Arms, and Chest. Each workout day is color-coded, and the script sorts exercises into their respective sheets. It also removes empty columns and formats the sheets with appropriate colors.

## Features

- **Color-Coded Separation**: 
  - **Legs** exercises are marked in blue (`#4a86e8`).
  - **Arms** exercises are marked in green (`#93c47d`).
  - **Chest** exercises are marked in red (`#e06666`).
  
- **Automatic Sheet Management**:
  - Exercises are copied to separate sheets (`Legs`, `Arms`, and `Chest`) based on the color in the leftmost column.
  - If these sheets do not exist, they are created automatically.
  - Existing data in the sheets is cleared before new data is added.
  
- **Header Handling**:
  - The header row from the active sheet is copied to each of the new sheets.
  
- **Empty Column Cleanup**:
  - The script automatically removes columns that only contain a header and no data in the `Legs`, `Arms`, and `Chest` sheets.

- **Color Formatting**:
  - The leftmost column in each of the new sheets is color-coded according to the workout category:
    - Blue for **Legs**.
    - Green for **Arms**.
    - Red for **Chest**.

## How It Works

1. **Check Leftmost Column for Colors**: 
   - The script scans the leftmost column of the active sheet to determine the category of each exercise based on the background color.
   
2. **Insert Data into Respective Sheets**:
   - Rows are copied into the appropriate sheet (Legs, Arms, or Chest) based on the color.
   - The script creates these sheets if they don’t exist and clears them if they do.

3. **Remove Empty Columns**:
   - After data insertion, the script removes any columns that contain only headers and no exercise data.
   
4. **Color Formatting**:
   - The leftmost column in each sheet is set to the corresponding color for Legs (blue), Arms (green), and Chest (red).

## Usage

To use this script, follow these steps:

1. **Open Your Google Sheet**:
   - Ensure your gym workout sheet has the leftmost column color-coded for Legs, Arms, and Chest days.
   
2. **Open Script Editor**:
   - Go to `Extensions > Apps Script` in the Google Sheets menu.

3. **Copy and Paste the Code**:
   - Copy the code from this repository and paste it into the Apps Script editor.

4. **Run the Script**:
   - You can manually run the `checkLeftmostColumnForSpecificHexes` function from the Apps Script editor, or you can set a trigger to run it automatically on a schedule.

5. **Enjoy the Organized Sheets**:
   - Your exercises will now be automatically separated into the `Legs`, `Arms`, and `Chest` sheets, and the sheets will be formatted accordingly.

## Functions Overview

### `checkLeftmostColumnForSpecificHexes()`
- Scans the leftmost column of the active sheet for color codes and inserts exercises into the corresponding sheets.
- Clears and formats the sheets accordingly.

### `insertHeaderIntoLegsSheet(sheetName, headerRowValues)`
- Inserts the header row into the specified sheet (`Legs`, `Arms`, or `Chest`).

### `insertValueIntoLegsSheet(sheetName, rowValues)`
- Inserts exercise data into the next available row in the specified sheet.

### `removeEmptyColumns(sheetName)`
- Removes columns that only contain the header row in the specified sheet.

### `setLeftmostColumnBackground(sheetName, color)`
- Sets the background color of the leftmost column in the specified sheet based on the workout category.

## Color Codes

- **Legs**: `#4a86e8` (Blue)
- **Arms**: `#93c47d` (Green)
- **Chest**: `#e06666` (Red)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
