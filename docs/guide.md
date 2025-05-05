# Setting Up Veda UI in Drupal

These instructions guide you through setting up the Veda Exploration and Analysis interface within a Drupal installation using Docker.

## 1. Clone the Repository

Clone the necessary repository from GitHub:
```
    git clone https://github.com/BhattaraiSijan/drupal-veda-mdx
```

2\. Get Drupal Running with Docker
----------------------------------

This documentation uses Docker for running Drupal. The repository includes a pre-configured `docker-compose.yml` file.

**Prerequisites:**

-   Ensure you have Docker Engine installed and running.

**Steps:**

1.  Navigate to the cloned repository directory in your terminal.

2.  Run the following command to start the Drupal container(s):


    ```
    docker compose up -d

    ```

3.  Verify that Drupal is running by accessing `http://localhost:8080` (or the port specified in your `docker-compose.yml` file) in your web browser.

3\. Configure Drupal Installation
---------------------------------

-   Follow the on-screen instructions provided by the Drupal web installer.
-   Database credentials (e.g., username, password, database name) needed during installation can be found within the `docker-compose.yml` file.
-   *Note: This example setup uses a PostgreSQL database.*

4\. Verify File Locations
-------------------------

Once Drupal is installed and running, ensure the following:

1.  The `veda_ui` folder exists inside `modules/custom`.
2.  The `uswds_base` folder (containing the USWDS base theme, version 3.8.1) exists inside `themes/contrib`.

5\. Install the Veda Module
---------------------------

1.  Navigate to the Drupal administration modules page: `/admin/modules`.
2.  Find the **Veda Module** in the list.
3.  Check the checkbox next to it.
4.  Scroll down and click the **Install** button.
5.  To verify successful installation, go to the configuration page: `/admin/config`. If you see a menu item named **Veda Settings**, the module installation was successful.

6\. Configure Veda Settings
---------------------------

1.  Navigate to the Veda settings page: `/admin/config/veda-ui/settings`.
2.  Enter your **Mapbox token**.
3.  Enter your **Raster API endpoint**.
4.  Enter your **STAC API endpoint**.
5.  Save the configuration.

7\. Initial Veda UI Check (Optional)
------------------------------------

At this point, you can navigate to `/veda-ui`. You should see the Veda Exploration and Analysis interface rendered, although the styling will likely be incorrect or missing.

8\. Install and Set the Theme
-----------------------------

1.  Navigate to the Drupal appearance page: `/admin/appearance`.
2.  Under the **Uninstalled themes** section, find the **USWDS base theme**.
3.  Click **Install and set as default**.

9\. Adjust Performance Settings
-------------------------------

1.  Navigate to the performance settings page: `/admin/config/development/performance`.
2.  **Uncheck** the following checkboxes:
    -   `Aggregate CSS files`
    -   `Aggregate Javascript files`
3.  Click **Save configuration**.

10\. Final Veda UI Check
------------------------

Navigate back to `/veda-ui`. The Veda Exploration and Analysis interface should now be displayed correctly with the proper styling.