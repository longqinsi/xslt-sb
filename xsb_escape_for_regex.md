# xsb:escape-for-regex(`input` _as_ `xs:string?`) #

Stylesheet: [strings.xsl](http://code.google.com/p/xslt-sb/source/browse/trunk/xslt-sb/strings.xsl)

## Parameter ##
`input`: String, der escapet werden soll



## Beschreibung ##
escapet Steuerzeichen in regulären Ausdrücken mit »`\`«

Ist `input` die Leersequenz, wird der Leerstring zurückgegeben.


**Beispiele**
  * `xsb:escape-for-regex('Jan.')` ergibt »`Jan\.`«
  * `xsb:escape-for-regex('^1.200$')` ergibt »`\^1\.200\$`«

### Versionen ###
| Revision | Datum | Autor | Beschreibung |
|:---------|:------|:------|:-------------|
| 0.2.47 | 2012-05-15 | Stf |   Status: alpha;   initiale Version   |


## Implementierung ##
```
<xsl:function xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:xsb="http://www.expedimentum.org/XSLT/SB" xmlns:intern="http://www.expedimentum.org/XSLT/SB/intern" xmlns:saxon="http://saxon.sf.net/" xmlns:doc="http://www.CraneSoftwrights.com/ns/xslstyle" xmlns:docv="http://www.CraneSoftwrights.com/ns/xslstyle/vocabulary" xmlns:xlink="http://www.w3.org/1999/xlink" name="xsb:escape-for-regex" as="xs:string">
		<xsl:param name="input" as="xs:string?"/>
		<xsl:sequence select="concat('', replace($input, '[\\*.+?\^\$()\[\]{}|]', '\\$0') )"/>
	</xsl:function>
```


---


_Hinweis: Die Dokumentation entstammt dem Stylesheet selbst, die Funktionen und Templates sind dort ausführlich dokumentiert._

_Hinweis: Diese Wiki-Seite wird automatisch aus der Dokumentation der einzenen Stylesheets der XSLT-SB erzeugt und soll deshalb nicht bearbeitet werden._

_Seite erstellt am 28.05.2012_