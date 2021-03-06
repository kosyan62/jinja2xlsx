# Changelog

## 0.3.1 - 18.10.2019

- Update openpyxl to ^3.0

## 0.3.0 - 18.05.2019

- jinja2xlsx.render.Renderer: parse img tag to image and add it to xlsx 

## 0.2.3 - 06.04.2019

### Fixed

- jinja2xlsx.utils.parse_cell_value: Check is float via isdigit with replace due to python crush on float(str)

### Removed 

- jinja2xlsx.render.Renderer: Remove lazy cell generation since there is no memory leak

## 0.2.2 - 06.04.2019

### Fixed

- jinja2xlsx.render.Renderer: lazy cell generation due to memory leak

## 0.2.1 - 01.04.2019 

### Fixed 

- None border as 0px border

## 0.2.0 - 01.04.2019

### Added 

- Imports in `__init__.py`:

    ```pydocstring
    # render func
    >>> from jinja2xlsx import render
    >>> from jinja2xlsx import render_xlsx
    # style class
    >>> from jinja2xlsx import Style
    ```

- Merge multiple borders:
    
    ```pydocstring
    >>> wb = render_xlsx("""<table>
    ...     <tbody>
    ...     <tr>
    ...         <td style="border: 1px solid black; border-bottom: 0">Cell without bottom border</td>
    ...     </tr>
    ...     </tbody>
    ... </table>""")
    >>> wb.active.cell.border
    Border(left=Side("thin"), right=Side("thin"), top=Side("thin"), bottom=Side())
    ```

## 0.1.0 - 24.03.2019

### Added 

- jinja2xlsx.api.render: render xlsx from html