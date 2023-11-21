# Bootiepie

Bootiepie is a UI Framework designed to simplify the process of creating printable reports. It utilizes a consistent naming convention to ensure clarity and organization:

* **hdr:** Represents a header component

* **txt:** Denotes a text component

* **img:** Indicates an image component

* **tab:** Represents a table component

* **crt:** Represents a chart component

Each HTML file follows this naming convention, facilitating easy identification of its components. For instance, `hdr-txt.html` is a preformatted component comprising a single header and a text paragraph. Similarly, `hdr-txt-txt` contains one header with two columns of text, and `hdr-txt-img` incorporates a header, text, and image.

## Getting Started

To utilize Bootiepie, follow these simple steps:

1. **Download the Bootiepie framework:** Acquire the latest version of Bootiepie from its official repository or website.

2. **Include Bootiepie in your project:** Integrate the Bootiepie framework into your project by referencing its corresponding JavaScript and CSS files.

3. **Create HTML templates:** Employ the specified naming convention (hdr, txt, img, tab, crt) to construct HTML templates for your report components.

4. **Assemble your report:** Combine the preformatted components (hdr-txt.html, hdr-txt-txt.html, etc.) to generate the final report.

## Using Bootiepie with Flask

To use Bootiepie with Flask, simply include the following line in your Flask application:

```python
from flask import render_template, Flask
app = Flask(__name__)
```

Then, create a route that renders the `btp-frame.html` template:

```python
@app.route("/")
def index():
    return render_template("bootiepie/btp-frame.html", title="My Title")
```

To add components to your report, progressively add content to the `content` variable:

```python
content = ""

# Add a header and text component
content += render_template("hdr-txt.html", hdr="Hi this is my heading", txt="this is my text. A very long text")

# Add an image component
content += render_template("img.html", img_src="https://example.com/image.jpg")

# Add a table component
content += render_template("tab.html", headers=["Name", "Age"], rows=[["John Doe", 30], ["Jane Doe", 25]])

# Add a chart component
content += render_template("crt.html", chart_type="bar", chart_data=[10, 20, 30, 40])

return render_template("bootiepie/btp-frame.html", title="My Title", content=content)
```

This will generate a report with the specified components.

### btp-frame.html

The `btp-frame.html` file serves as the main report frame. It contains all the necessary CSS styling and Bootstrap CDN libraries to ensure consistent formatting across report components.

## Benefits

Bootiepie offers several advantages for creating printable reports:

* **Simplified Component Creation:** The consistent naming convention streamlines the process of creating and organizing report components.

* **Modular Design:** The framework's modular approach allows for easy reuse and customization of components, fostering consistency and maintainability.

* **Enhanced Efficiency:** Bootiepie promotes efficient report generation by minimizing code duplication and simplifying component management.

## Examples

The Bootiepie documentation provides comprehensive examples and tutorials to guide users in creating various report layouts and incorporating diverse components.

## Contributing

Bootiepie welcomes contributions from the developer community. If you're interested in contributing to the framework's development, please refer to the contribution guidelines provided in the project's documentation.
