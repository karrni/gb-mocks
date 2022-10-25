# Formatvorlagen

![](<../../.gitbook/assets/image (18).png>)

## Built-In Styles

Microsoft Word beinhaltet eine Reihe vordefinierter Formatvorlagen (Built-In Styles). Diese werden in den darunterliegenden xml Dateien immer unter ihren englischen Namen gespeichert. Word selbst übersetzt aber automatisch in die jeweilig installierte Sprache. Das hat zurfolge, dass gewisse Formatvorlagen wie Überschriften als "heading 1" gespeichert, aber als Überschrift 1 angezeigt werden.

Eine kurze Beschreibung dieses Verhaltens im Wiki der python-docx Bibliothek:

{% embed url="https://python-docx.readthedocs.io/en/latest/user/styles-using.html" %}

Ein Liste von Mappings der englischen Bezeichnungen zu den deutschen:

{% embed url="https://www.thedoctools.com/word-macros-tips/word-tips/word-style-names-in-english-danish-german-french" %}

## Formatvorlagenkatalog

Es werden nicht alle Formatvorlagen im Formatvorlagenkatalog angezeigt. Ob eine Vorlage aufscheinen soll, wird durch den `qFormat` Tag kontrolliert. Hat der jeweilige Style diesen Tag gesetzt, führt Word ihn im Katalog an.

```xml
<w:style w:type="paragraph" w:default="1" w:styleId="Standard">
    <w:name w:val="Normal"/>
    <w:qFormat/>
</w:style>
```

{% embed url="https://c-rex.net/projects/samples/ooxml/e1/Part4/OOXML_P4_DOCX_qFormat_topic_ID0EDEQT.html" %}
