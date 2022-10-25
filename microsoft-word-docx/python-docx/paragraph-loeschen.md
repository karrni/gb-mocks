# Paragraph löschen

Zum Zeitpunkt der Erstellung dieses Artikels verfügt python-docx nicht über eine Funktion zum Löschen eines bestimmten Absatzes. Die folgende Funktion implementiert dies:

```python
def delete_paragraph(paragraph):
    p = paragraph._element
    p.getparent().remove(p)
    p._p = p._element = None
```

### Referenz

{% embed url="https://github.com/python-openxml/python-docx/issues/33#issuecomment-77661907=" %}
