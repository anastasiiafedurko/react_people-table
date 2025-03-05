# React People Table

This project implements a React-based app to display and filter a list of people, with features such as sorting, filtering by name, sex, century, and more. It includes two main pages: **HomePage** and **PeoplePage**.

## Features

- **HomePage**: Available at `/` with the title **Home Page**.
- **PeoplePage**: Available at `/people` with the title **People Page**, where people data is fetched from an API and displayed in a table.
- **NotFoundPage**: A fallback page that is displayed for any URL that does not match the existing routes.
- **Navbar**: Contains two links: **Home** and **People**. The active link is highlighted with the `has-background-grey-lighter` class.
- **HashRouter**: Used to ensure URLs can be shared and the app works correctly on GitHub Pages.
- **API Integration**: Fetches people data from an API when the PeoplePage is opened and displays it in a table.

## Key Features

- **Navigation**:

  - Navigate between HomePage and PeoplePage using React Router's `Navigate` component.
  - The `replace` attribute in `Navigate` ensures the `/home` URL is not stored in the browser's history, preventing navigation loops when pressing the "Go Back" button.

- **People Table**:

  - The PeoplePage displays a table with people’s names, birth and death years, and parent names.
  - Each person’s name is a clickable link to their details page `/people/:slug`.
  - Women’s names are highlighted using the `has-text-danger` class.
  - The table row of the selected person is highlighted with the `has-background-warning` class.

- **Filters and Sorting**:
  - The **NameFilter** allows you to search for people by name, mother’s name, or father’s name.
  - **CenturyFilter** allows you to filter people by century, and the filter uses URL search parameters to store the selected centuries.
  - Sorting by name, sex, born, and died is implemented using clickable table headers (`th`). Sorting is toggled by clicking on the column, and the sort order is saved in the URL search parameters.
  - Sorting by column is implemented with three states: ascending, descending, and disabled.
  - The filters and sort parameters are stored as URL search params, making the app's state shareable via the URL.

## Project Structure

- **src/components**:

  - `Navbar`: A navigation bar with links to the HomePage and PeoplePage.
  - `PeopleTable`: Renders the table of people with filters, sorting, and active row highlighting.
  - `PersonLink`: A component that generates a link for each person, including links for their mother and father.
  - `NameFilter`: Allows the user to search by name, mother’s name, or father’s name.
  - `CenturyFilter`: Allows the user to filter by century.
  - `NotFoundPage`: Displays the "Page not found" message for non-existing routes.

- **src/pages**:
  - `HomePage`: Displays a simple "Home Page" message.
  - `PeoplePage`: Fetches and displays the list of people, allows filtering and sorting.
  - `NotFoundPage`: Displays for all non-matching routes.

## Usage

1. **Clone the repository**:

   ```bash
   git clone https://github.com/anastasiiafedurko/react_people-table.git
   cd react_people-table
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

3. **Run the app locally**:

   ```bash
   npm start
   ```

   This will start the development server at `http://localhost:3000`. Open it in your browser to see the application in action.

4. **Build the app for deployment**:

   ```bash
   npm run build
   ```

   This will create an optimized production build in the `build/` folder.

5. **Deploy on GitHub Pages**:

   After building the app, you can deploy it to GitHub Pages by running:

   ```bash
   npm run deploy
   ```

   This will deploy the app to the GitHub Pages URL.

## URL Parameters

- **Query**: Use the `query` URL parameter to search for people by name, mother’s name, or father’s name. For example: `/people?query=John`.
- **Century**: Use the `centuries` URL parameter to filter people by their birth or death century. You can select multiple centuries. For example: `/people?centuries=17&centuries=18`.
- **Sort**: Use the `sort` URL parameter to control the sorting of the table by `name`, `sex`, `born`, or `died`. The `order` parameter can be used to specify descending order (e.g., `/people?sort=name&order=desc`).
- **Navigation**: The `replace` attribute is used to prevent storing `/home` in the browser history during navigation between pages.

## Technologies Used

- **React**: Front-end JavaScript library for building user interfaces.
- **React Router**: For routing and navigation between pages.
- **Vite**: A modern build tool that provides fast development and production build processes.
- **GitHub Pages**: For deploying the app.

## Conclusion

This project demonstrates how to create a React app with dynamic pages, filtering, sorting, and navigation features. By using URL search parameters for filters and sorting, the state of the app is shareable and maintainable.
