# FlatDango Documentation

This project is a simple Movie App that fetches movie data from a server and displays it in the browser. Users can view movie details and buy tickets for available movies.

---

## Features
1. Displays the details of the first movie on page load.
2. Dynamically fetches and displays a list of all available movies.
3. Updates movie details when a movie from the list is clicked.
4. Allows users to buy tickets for movies with available capacity.
5. Disables the "Buy Ticket" button and marks movies as "Sold Out" when all tickets are sold.

---

## File Structure

### HTML Elements Referenced
- **`#poster`**: Displays the poster image of the selected movie.
- **`#title`**: Shows the title of the selected movie.
- **`#runtime`**: Displays the runtime of the selected movie.
- **`#showtime`**: Shows the showtime of the selected movie.
- **`#available-tickets`**: Displays the number of tickets available for the selected movie.
- **`#buy-ticket`**: Button to purchase a ticket for the selected movie.
- **`#films`**: A list element where all movie titles are dynamically displayed.

---

## How It Works

### Initialization
The script initializes the application by:
1. Fetching details of the first movie and displaying it.
2. Fetching the list of all movies and populating the sidebar with movie titles.

### Movie Details Update
- **`updateMovieDetails(movie)`**: Updates the details section with the selected movie's data (poster, title, runtime, showtime, available tickets).
- Adjusts the "Buy Ticket" button based on ticket availability.
- Handles ticket purchase logic.

### Movie List Creation
- **`createFilmListItem(movie)`**: Dynamically creates a list item for each movie.
- Marks sold-out movies with a specific class.
- Adds a click event to fetch and display the details of the clicked movie.

---

## API Endpoints
The application uses a local server (`http://localhost:3000`) for fetching movie data.

### Endpoints:
1. **`GET /films/1`**: Fetches details of the first movie.
2. **`GET /films`**: Fetches a list of all movies.
3. **`GET /films/:id`**: Fetches details of a specific movie by its ID.

---

## Key Functions

### 1. **fetchFirstMovie()**
- Fetches details of the first movie from the server.
- Calls `updateMovieDetails(movie)` to display the fetched data.

### 2. **fetchMovieList()**
- Fetches the list of all movies from the server.
- Calls `createFilmListItem(movie)` for each movie to populate the movie list.

### 3. **updateMovieDetails(movie)**
- Updates the DOM elements to show the selected movie's details.
- Handles ticket availability and purchase logic.

### 4. **createFilmListItem(movie)**
- Creates a clickable list item for each movie.
- Marks movies as "Sold Out" if no tickets are available.
- Adds an event listener to fetch and display the details of the clicked movie.

---

## Styling Considerations
- **Classes used:**
  - `film`: Base class for each movie list item.
  - `item`: Additional class for list styling.
  - `sold-out`: Indicates movies with no available tickets.

---

## How to Run the App
1. Ensure a local server (e.g., JSON Server) is running at `http://localhost:3000` with the appropriate movie data.
2. Include the script in an HTML file with the required DOM structure (e.g., `#poster`, `#title`, `#films`, etc.).
3. Open the HTML file in a browser to interact with the app.

---

## Example JSON Data
Below is an example of the data expected from the server:

```json
[
  {
    "id": 1,
    "title": "The Great Adventure",
    "runtime": "120 mins",
    "showtime": "7:00 PM",
    "capacity": 100,
    "tickets_sold": 60,
    "poster": "https://example.com/poster1.jpg"
  },
  {
    "id": 2,
    "title": "Mystery Island",
    "runtime": "90 mins",
    "showtime": "5:30 PM",
    "capacity": 80,
    "tickets_sold": 80,
    "poster": "https://example.com/poster2.jpg"
  }
]
```

---

## Future Improvements
- Add support for dynamic ticket updates on the server.
- Implement search functionality to filter the movie list.
- Enhance UI/UX with better styles and animations.
- Handle edge cases, such as server errors or empty responses.

---

## Troubleshooting
1. **Error fetching movie list or details**:
   - Ensure the local server is running at `http://localhost:3000`.
   - Verify the API endpoints and JSON data structure.
2. **Buy Ticket button not working**:
   - Check if the `onclick` handler is properly set in `updateMovieDetails()`.

---

