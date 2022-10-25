# Überschrift 1

{% code title="word/styles.xml" %}
```xml
<w:style w:type="paragraph" w:styleId="berschrift1">
    <w:name w:val="heading 1"/>
    <w:basedOn w:val="Standard"/>
    <w:next w:val="Standard"/>
    <w:link w:val="berschrift1Zchn"/>
    <w:uiPriority w:val="9"/>
    <w:qFormat/>
    <w:pPr>
        <w:keepNext/>
        <w:pageBreakBefore/>
        <w:numPr>
            <w:numId w:val="2"/>
        </w:numPr>
        <w:spacing w:before="240"/>
        <w:outlineLvl w:val="0"/>
    </w:pPr>
    <w:rPr>
        <w:b/>
        <w:sz w:val="32"/>
        <w:szCs w:val="32"/>
    </w:rPr>
</w:style>

<w:style w:type="character" w:customStyle="1" w:styleId="berschrift1Zchn">
    <w:name w:val="Überschrift 1 Zchn"/>
    <w:basedOn w:val="Absatz-Standardschriftart"/>
    <w:link w:val="berschrift1"/>
    <w:uiPriority w:val="9"/>
    <w:rPr>
        <w:b/>
        <w:sz w:val="32"/>
        <w:szCs w:val="32"/>
    </w:rPr>
</w:style>
```
{% endcode %}
