# Generate a new project

1. **Install Genesia**
   ```bash
   pip install genesia
   ```

2. **Create a new project**
   ```bash
   genesia create --name "myproject" --template "django" --prompt "Hotel Booking API"
   ```
   Replace "myproject" with the name you want for your project.

3. **Install Django**:
   ```bash
   pip install django
   ```

4. **Navigate to the project directory**: 
   ```bash
   cd myproject
   ```

5. **Run Migrations**: To create the database tables for your models, run:
   ```
   python manage.py makemigrations app
   python manage.py migrate
   ```

6. **Create Superuser**: To access the admin site, create a superuser:
   ```
   python manage.py createsuperuser
   ```

7. **Run the Development Server**: Start the development server:
   ```
   python manage.py runserver
   ```



# Update an existing project

When developing a Django project, depending on what you modify, you might need to rerun certain commands. Here's a general guideline:

1. **Changes to Models**: If you make changes to the models in `models.py` (like adding/removing fields, changing relationships), you'll need to create and apply new migrations:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

2. **Changes to Static Files or Templates**: If you're using Django's static files handling or templates and make changes to them, you usually don't need to rerun any specific command during development. The development server should pick up these changes automatically.

3. **Changes to Python Code**: If you make changes to views, URLs, settings, or other Python code, the development server usually automatically reloads the code. However, if you make changes to the settings file or encounter issues with code reloading, you might need to manually restart the development server:
   ```bash
   python manage.py runserver
   ```

4. **Adding a New Admin Interface**: If you add a new model to the admin interface in `admin.py`, you don't need to rerun anything specific; changes should be reflected automatically on the admin site.

5. **Changes to Tests**: If you modify or add tests, you'll need to rerun the test command to execute them:
   ```bash
   python manage.py test
   ```

6. **Installing a New App or Library**: If you add a new app to `INSTALLED_APPS` or install a new Python library, you'll likely want to restart the development server to ensure that the new code is picked up.

7. **Changes to ASGI or WSGI Configuration**: If you modify `asgi.py` or `wsgi.py`, these changes typically require a server restart, especially in a production environment.

