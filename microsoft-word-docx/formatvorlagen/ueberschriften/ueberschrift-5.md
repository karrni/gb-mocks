# Überschrift 5

{% code title="word/styles.xml" %}
```xml
<w:style w:type="paragraph" w:styleId="berschrift5">
    <w:name w:val="heading 5"/>
    <w:basedOn w:val="Standard"/>
    <w:next w:val="Standard"/>
    <w:link w:val="berschrift5Zchn"/>
    <w:uiPriority w:val="9"/>
    <w:qFormat/>
    <w:pPr>
        <w:keepNext/>
        <w:spacing w:before="120"/>
        <w:outlineLvl w:val="3"/>
    </w:pPr>
    <w:rPr>
        <w:u w:val="single"/>
    </w:rPr>
</w:style>

<w:style w:type="character" w:customStyle="1" w:styleId="berschrift5Zchn">
    <w:name w:val="Überschrift 5 Zchn"/>
    <w:basedOn w:val="Absatz-Standardschriftart"/>
    <w:link w:val="berschrift5"/>
    <w:uiPriority w:val="9"/>
    <w:rPr>
        <w:u w:val="single"/>
        <w:sz w:val="20"/>
    </w:rPr>
</w:style>
```
{% endcode %}
