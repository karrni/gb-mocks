# Standard

Der _Standard Paragraph Style_ definiert die Schriftart und die Abstände zwischen Paragraphen:

{% code title="word/styles.xml" %}
```xml
<w:style w:type="paragraph" w:default="1" w:styleId="Standard">
    <w:name w:val="Normal"/>
    <w:qFormat/>
    <w:pPr>
        <w:spacing w:before="120" w:after="120" w:line="240" w:lineRule="auto"/>
        <w:jc w:val="both"/>
    </w:pPr>
    <w:rPr>
        <w:rFonts w:ascii="Arial" w:hAnsi="Arial"/>
        <w:sz w:val="20"/>
    </w:rPr>
</w:style>
```
{% endcode %}
