---
title: "Secuencias de comandos mediante XSLT en línea y plantillas de llamada XSLT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3168417-3653-4c9e-a09c-184ffdc0ccb2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c4c1d8eff582d15f9ce022053b80f2dea2f856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a>Crear secuencias de comandos mediante XSLT en línea y plantillas de llamada XSLT en línea
Puede escribir directamente hojas de estilos Extensible Stylesheet Language Transformations (XSLT) para su uso en el **secuencias de comandos** functoid. Esto le permite realizar transformaciones que tal vez los vínculos y functoids integrados no sean capaces de representar. Hay dos tipos de secuencias de comandos XSLT: en línea plantillas de llamada XSLT y XSLT. Cuando selecciona una de ellas en el **Seleccionar tipo de script** lista desplegable en el **configurar Functoid de script** cuadro de diálogo, aparece el código de ejemplo que puede utilizar.  
  
 Las plantillas de secuencias de comandos XSLT en línea y llamada XSLT en línea pueden llamar funciones en ensamblados externos. Para realizar esas llamadas requiere la configuración del **XML de extensión personalizada** propiedad de la cuadrícula. Para obtener más información, consulte **XML de extensión personalizada (propiedad de cuadrícula)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="inline-xslt"></a>XSLT en línea  
 Una secuencia de comandos XSLT en línea solo puede producir salidas. El **secuencias de comandos** functoid no puede tener vínculos de entrada. El functoid también debe vincular directamente a un registro o campo en el esquema de destino.  
  
 Además, la secuencia de comandos es responsable de la creación del nodo de destino y cualquier estructura que esté debajo de él.  
  
 El siguiente mensaje de instancia de entrada contiene dos elementos que representan información de contacto.  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 El siguiente script XSLT en línea, en el búfer de secuencia de comandos, convierte el **póngase en contacto con** y **ContactType** campos a los atributos.  
  
```  
<ContactInfo xmlns:p="http://SourceInstanceNamespace">  
     <xsl:variable name="var:var1" select="/p:SourceInstance/Address/ContactType" />  
     <xsl:attribute name="ContactType">  
          <xsl:value-of select="$var:var1" />  
     </xsl:attribute>  
     <xsl:variable name="var:var2" select="/p:SourceInstance/Address/Contact" />  
     <xsl:attribute name="Contact">  
          <xsl:value-of select="$var:var2" />  
     </xsl:attribute>  
</ContactInfo>  
```  
  
 La secuencia de comandos crea la siguiente salida, suponiendo que el esquema de salida sea el adecuado, cuando se ejecuta con respecto al mensaje de instancia de entrada anterior.  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 Tenga en cuenta que la ausencia de vínculos a la **secuencias de comandos** functoid no impide que la secuencia de comandos XSLT obtener datos desde el mensaje de instancia de entrada. La secuencia de comandos especifica rutas a los valores de instancia de entrada.  
  
 Para obtener otro ejemplo de una secuencia de comandos XSLT en línea, consulte [herramientas de XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md).  
  
## <a name="inline-xslt-call-templates"></a>Plantillas de llamada XSLT en línea  
 Al igual que una secuencia de comandos XSLT en línea, una plantilla de llamada XSLT en línea debe conectar directamente con un nodo de destino. Sin embargo, una plantilla de llamada XSLT en línea puede utilizar vínculos del esquema de origen y de otros functoids.  
  
 La plantilla de llamada es responsable de la creación del nodo de destino y todas sus subestructuras.  
  
 Aparece una plantilla de llamada XSLT de ejemplo que concatena dos elementos en el **de entrada de secuencia de comandos** almacenar en búfer cuando se selecciona **plantilla de llamada de XSLT en línea** en el **Seleccionar tipo de script** lista desplegable.  
  
 Para obtener otro ejemplo de una plantilla de llamada XSLT en línea, consulte [herramientas de XML (carpeta de ejemplos de BizTalk Server)](../core/xml-tools-biztalk-server-samples-folder.md).  
  
## <a name="see-also"></a>Vea también  
 [Secuencias de comandos de Functoid](../core/scripting-functoid.md)   
 [Secuencias de comandos con ensamblados externos](../core/scripting-using-external-assemblies.md)   
 [Secuencias de comandos mediante C# en línea, JScript .NET y Visual Basic .NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [Cómo agregar Functoids de Scripting a un mapa](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [Cómo configurar el Functoid de secuencias de comandos](../core/how-to-configure-the-scripting-functoid.md)