# Aufzählung

Eine Liste mit Aufzählungspunkten. Die erste Ebene soll bündig mit dem Fließtext verlaufen und Einrückungen sollen kleiner und einheitlich sein.

![](<../../.gitbook/assets/image (1) (1).png>)

{% hint style="info" %}
Im folgenden sind alle IDs aus einem Beispieldokument entnommen. Gegebenenfalls müssen sie angepasst werden, damit keine Kollisionen mit vorhandenen Einträgen entstehen.
{% endhint %}

Alle notwendigen Definitionen finden sich in `word/numbering.xml` und `word/styles.xml`. Demnach müssen diese in `[Content_Types].xml` angeführt sein:

{% code title="[Content_Types].xml" %}
```xml
<Override PartName="/word/numbering.xml" ContentType="application/vnd.openxmlformats-officedocument.wordprocessingml.numbering+xml"/>
<Override PartName="/word/styles.xml" ContentType="application/vnd.openxmlformats-officedocument.wordprocessingml.styles+xml"/>
```
{% endcode %}

Außerdem muss in der `word/_rels/document.xml.rels` Datei ein Eintrag für das beide Dateien vorhanden sein:

{% code title="word/_rels/document.xml.rels" %}
```xml
<Relationship Id="rId1" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles" Target="styles.xml"/>
<Relationship Id="rId6" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/numbering" Target="numbering.xml"/>
```
{% endcode %}

Ausgangsformat ist die Vorlage _Standard_. Der _Paragraph Style_ definiert die Breite des Tabstopps und verweist auf einen _Numbering Style_:

{% code title="word/styles.xml" %}
```xml
<w:style w:type="paragraph" w:styleId="Aufzhlung">
    <w:name w:val="Aufzählung"/>
    <w:basedOn w:val="Standard"/>
    <w:uiPriority w:val="34"/>
    <w:qFormat/>
    <w:pPr>
        <w:numPr>
            <w:numId w:val="12"/>
        </w:numPr>
        <w:tabs>
            <w:tab w:val="left" w:pos="357"/>
        </w:tabs>
    </w:pPr>
</w:style>
```
{% endcode %}

Dieser _Numbering Style_ definiert das Aufzählungszeichen und die genaue Einrückung aller acht Einrückungsstufen:

{% code title="word/numbering.xml" %}
```xml
<w:abstractNum w:abstractNumId="3" w15:restartNumberingAfterBreak="0">
    <w:nsid w:val="24A204DA"/>
    <w:multiLevelType w:val="multilevel"/>
    <w:tmpl w:val="77D82036"/>
    <w:lvl w:ilvl="0">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:pStyle w:val="Aufzhlung"/>
        <w:lvlText w:val=""/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="357" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Symbol" w:hAnsi="Symbol" w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="1">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:lvlText w:val="o"/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="595" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Courier New" w:hAnsi="Courier New" w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="2">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:lvlText w:val=""/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="833" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Wingdings" w:hAnsi="Wingdings" w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="3">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:lvlText w:val=""/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="1071" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Symbol" w:hAnsi="Symbol" w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="4">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:lvlText w:val="o"/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="1309" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Courier New" w:hAnsi="Courier New" w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="5">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:lvlText w:val=""/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="1547" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Wingdings" w:hAnsi="Wingdings" w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="6">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:lvlText w:val=""/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="1785" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Symbol" w:hAnsi="Symbol" w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="7">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:lvlText w:val="o"/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="2023" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Courier New" w:hAnsi="Courier New" w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="8">
        <w:start w:val="1"/>
        <w:numFmt w:val="bullet"/>
        <w:lvlText w:val=""/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="2261" w:hanging="357"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:ascii="Wingdings" w:hAnsi="Wingdings" w:hint="default"/>
        </w:rPr>
    </w:lvl>
</w:abstractNum>

<w:num w:numId="12">
    <w:abstractNumId w:val="3"/>
</w:num>
```
{% endcode %}
