# Überschrift 4

{% code title="word/styles.xml" %}
```xml
<w:style w:type="paragraph" w:styleId="berschrift4">
    <w:name w:val="heading 4"/>
    <w:basedOn w:val="Standard"/>
    <w:next w:val="Standard"/>
    <w:link w:val="berschrift4Zchn"/>
    <w:uiPriority w:val="9"/>
    <w:qFormat/>
    <w:pPr>
        <w:keepNext/>
        <w:spacing w:before="240"/>
        <w:outlineLvl w:val="3"/>
    </w:pPr>
    <w:rPr>
        <w:b/>
    </w:rPr>
</w:style>

<w:style w:type="character" w:customStyle="1" w:styleId="berschrift4Zchn">
    <w:name w:val="Überschrift 4 Zchn"/>
    <w:basedOn w:val="Absatz-Standardschriftart"/>
    <w:link w:val="berschrift4"/>
    <w:uiPriority w:val="9"/>
    <w:rPr>
        <w:b/>
        <w:sz w:val="20"/>
    </w:rPr>
</w:style>
```
{% endcode %}
