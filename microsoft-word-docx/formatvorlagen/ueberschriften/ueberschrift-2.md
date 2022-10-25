# Überschrift 2

{% code title="word/styles.xml" %}
```xml
<w:style w:type="paragraph" w:styleId="berschrift2">
    <w:name w:val="heading 2"/>
    <w:basedOn w:val="Standard"/>
    <w:next w:val="Standard"/>
    <w:link w:val="berschrift2Zchn"/>
    <w:uiPriority w:val="9"/>
    <w:qFormat/>
    <w:pPr>
        <w:keepNext/>
        <w:keepLines/>
        <w:numPr>
            <w:ilvl w:val="1"/>
            <w:numId w:val="2"/>
        </w:numPr>
        <w:spacing w:before="360" w:after="0"/>
        <w:contextualSpacing/>
        <w:outlineLvl w:val="1"/>
    </w:pPr>
    <w:rPr>
        <w:b/>
        <w:sz w:val="28"/>
        <w:szCs w:val="26"/>
    </w:rPr>
</w:style>

<w:style w:type="character" w:customStyle="1" w:styleId="berschrift2Zchn">
    <w:name w:val="Überschrift 2 Zchn"/>
    <w:basedOn w:val="Absatz-Standardschriftart"/>
    <w:link w:val="berschrift2"/>
    <w:uiPriority w:val="9"/>
    <w:rPr>
        <w:b/>
        <w:sz w:val="28"/>
        <w:szCs w:val="26"/>
    </w:rPr>
</w:style>
```
{% endcode %}
