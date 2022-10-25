# Überschrift 3

{% code title="word/styles.xml" %}
```xml
<w:style w:type="paragraph" w:styleId="berschrift3">
    <w:name w:val="heading 3"/>
    <w:basedOn w:val="Standard"/>
    <w:next w:val="Standard"/>
    <w:link w:val="berschrift3Zchn"/>
    <w:uiPriority w:val="9"/>
    <w:qFormat/>
    <w:pPr>
        <w:keepNext/>
        <w:keepLines/>
        <w:numPr>
            <w:ilvl w:val="2"/>
            <w:numId w:val="2"/>
        </w:numPr>
        <w:spacing w:before="360"/>
        <w:outlineLvl w:val="2"/>
    </w:pPr>
    <w:rPr>
        <w:b/>
        <w:sz w:val="22"/>
        <w:szCs w:val="24"/>
    </w:rPr>
</w:style>

<w:style w:type="character" w:customStyle="1" w:styleId="berschrift3Zchn">
    <w:name w:val="Überschrift 3 Zchn"/>
    <w:basedOn w:val="Absatz-Standardschriftart"/>
    <w:link w:val="berschrift3"/>
    <w:uiPriority w:val="9"/>
    <w:rPr>
        <w:b/>
        <w:szCs w:val="24"/>
    </w:rPr>
</w:style>
```
{% endcode %}
