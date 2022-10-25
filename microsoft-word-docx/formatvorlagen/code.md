# Code

{% code title="word/styles.xml" %}
```xml
<w:style w:type="paragraph" w:customStyle="1" w:styleId="SourceCode">
    <w:name w:val="Source Code"/>
    <w:basedOn w:val="Standard"/>
    <w:link w:val="SourceCodeChar"/>
    <w:qFormat/>
    <w:pPr>
        <w:pBdr>
            <w:top w:val="single" w:sz="4" w:space="4" w:color="auto"/>
            <w:left w:val="single" w:sz="4" w:space="4" w:color="auto"/>
            <w:bottom w:val="single" w:sz="4" w:space="4" w:color="auto"/>
            <w:right w:val="single" w:sz="4" w:space="4" w:color="auto"/>
        </w:pBdr>
        <w:shd w:val="clear" w:color="auto" w:fill="E7E6E6" w:themeFill="background2"/>
        <w:spacing w:before="0" w:after="0"/>
    </w:pPr>
    <w:rPr>
        <w:rFonts w:ascii="Consolas" w:hAnsi="Consolas"/>
        <w:noProof/>
        <w:sz w:val="16"/>
    </w:rPr>
</w:style>
<w:style w:type="character" w:customStyle="1" w:styleId="SourceCodeChar">
    <w:name w:val="Source Code Char"/>
    <w:basedOn w:val="Absatz-Standardschriftart"/>
    <w:link w:val="SourceCode"/>
    <w:rPr>
        <w:rFonts w:ascii="Consolas" w:hAnsi="Consolas"/>
        <w:noProof/>
        <w:sz w:val="16"/>
        <w:shd w:val="clear" w:color="auto" w:fill="E7E6E6" w:themeFill="background2"/>
    </w:rPr>
</w:style>
```
{% endcode %}
