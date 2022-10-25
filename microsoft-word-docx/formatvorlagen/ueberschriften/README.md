# Überschriften

{% hint style="warning" %}
Der Grund, warum die Formatvorlagen unter ihren englischen Namen abgespeichert werden ist im Überkapitel Formatvorlagen beschrieben.\
\
Es ist wichtig, die Standard Formatvorlagen zu verwenden, damit die docx Dateien ggf. mit Tools wie pandoc korrekt in bspw. Markdown umgewandelt werden können. Eingebaute Formatvorlagen wie _heading 1-4_ werden als Überschriften erkannt - eigens erstellte wie _Report Überschrift_ nicht.
{% endhint %}

![](<../../../.gitbook/assets/image (3) (1).png>)

Überschriften bestehen aus einem _Paragraph Style_ und einem _Character Style_ und es wird ein Nummerierungsschema referenziert. Folgende Definitionen sind die Grundlage für die Überschriften:

### Absatz-Standardschriftart

{% code title="word/styles.xml" %}
```xml
<w:style w:type="character" w:default="1" w:styleId="Absatz-Standardschriftart">
    <w:name w:val="Default Paragraph Font"/>
    <w:uiPriority w:val="1"/>
    <w:hidden/>
</w:style>
```
{% endcode %}

### Nummerierung

{% code title="word/numbering.xml" %}
```xml
<w:abstractNum w:abstractNumId="6" w15:restartNumberingAfterBreak="0">
    <w:nsid w:val="4B4313A1"/>
    <w:multiLevelType w:val="multilevel"/>
    <w:tmpl w:val="037E5528"/>
    <w:lvl w:ilvl="0">
        <w:start w:val="1"/>
        <w:numFmt w:val="decimal"/>
        <w:pStyle w:val="berschrift1"/>
        <w:lvlText w:val="%1"/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="432" w:hanging="432"/>
        </w:pPr>
        <w:rPr>
            <w:rFonts w:hint="default"/>
        </w:rPr>
    </w:lvl>
    <w:lvl w:ilvl="1">
        <w:start w:val="1"/>
        <w:numFmt w:val="decimal"/>
        <w:pStyle w:val="berschrift2"/>
        <w:lvlText w:val="%1.%2"/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="576" w:hanging="576"/>
        </w:pPr>
    </w:lvl>
    <w:lvl w:ilvl="2">
        <w:start w:val="1"/>
        <w:numFmt w:val="decimal"/>
        <w:pStyle w:val="berschrift3"/>
        <w:lvlText w:val="%1.%2.%3"/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="720" w:hanging="720"/>
        </w:pPr>
    </w:lvl>
    <w:lvl w:ilvl="3">
        <w:start w:val="1"/>
        <w:numFmt w:val="decimal"/>
        <w:pStyle w:val="berschrift4"/>
        <w:lvlText w:val="%1.%2.%3.%4"/>
        <w:lvlJc w:val="left"/>
        <w:pPr>
            <w:ind w:left="864" w:hanging="864"/>
        </w:pPr>
    </w:lvl>
</w:abstractNum>

<w:num w:numId="2">
    <w:abstractNumId w:val="6"/>
</w:num>
```
{% endcode %}
