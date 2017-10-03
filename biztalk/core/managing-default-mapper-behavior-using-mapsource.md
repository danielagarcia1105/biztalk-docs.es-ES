---
title: Administrar el comportamiento de asignador predeterminado mediante &lt;mapsource&gt; | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: deea839c-e52e-44c6-ac0d-4396dc5b10d8
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44e2e66350709c6b857d875ec3979fe3f7059648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-default-mapper-behavior-using-ltmapsourcegt"></a>Administrar el comportamiento de asignador predeterminado mediante &lt;mapsource&gt;
Puede modificar ciertos comportamientos predeterminados del asignador de BizTalk mediante la modificación de atributos de la **mapsource** elemento directamente en un archivo de origen (.btm) de asignación.  
  
## <a name="optimizing-value-mapping-functoid-code-generation"></a>Optimizar la generación del código de functoid Asignación de valores  
 Cuando el asignador genera código XSLT para llamar a la **Value Mapping** functoid, una variable se usa para almacenar el resultado. Puede usar el **OptimizeValueMapping** marca para optimizar el **Value Mapping** functoid para que se genere una variable solo cuando la `if` instrucción se evalúa como `True`. Por ejemplo, con **OptimizeValueMapping** establecido en **n**:  
  
```  
<xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 Este código podría optimizarse trasladando la **Value Mapping** invocación al functoid en el cuerpo de la `if` instrucción, asegurándose de que la invocación produce solo cuando es necesario. Establecer **OptimizeValueMapping** a **Sí** produce el siguiente código:  
  
```  
<xsl:if test="string($var:v4)='true'">  
     <xsl:variable name="var:v5" select="ScriptNS0:FormatMessage(…)" />  
     <xsl:variable name="var:v6" select="string($var:v5)" />  
     <ns0:text>  
          <xsl:value-of select="$var:v6" />  
     </ns0:text>  
</xsl:if>  
```  
  
 El asignador realiza esta optimización automáticamente si se establece la **OptimizeValueMapping** atributo de la **mapsource** elemento en el archivo de origen (.btm) asignación **Sí** como se muestra:  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="Yes" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
## <a name="accommodating-schemas-with-large-footprints"></a>Dar cabida a esquemas con huellas grandes  
 Cuando el Asignador usa un esquema que tiene una huella de instancia muy grande, con estructuras complejas profundas o nodos recursivos, puede ser necesario mucho tiempo para probar, validar o compilar la asignación; en el peor de los casos, puede producirse un error por memoria insuficiente. Esto puede ocurrir tanto con pequeños esquemas complejos como con esquemas grandes.  
  
 El problema con esquemas complejos es debido al hecho de que el asignador tiene que cargar recursivamente el árbol de esquema todo busca de nodos que tienen vínculos conectados o la **valor** propiedad establecida en ellos. Puede mitigar este problema estableciendo la **GenerateDefaultFixedNodes** marca de la **mapsource** elemento en los archivos .btm en **n** tal como se muestra:  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="No" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 Con esta configuración, el Asignador no necesita crear nodos de compilador interno asociados a cada nodo de esquema de un esquema de destino. El compilador sólo tendrá en cuenta los nodos vinculados. Esto reduce significativamente el consumo de memoria y agiliza el proceso al realizar una operación "comprobar asignación" o "validar asignación", al compilar una asignación o al guardarla.  
  
 Sin embargo, cuando la **GenerateDefaultFixedNodes** marca se establece en **No**, los valores de campo predeterminados, establecidos en el esquema de destino no se conservan en la instancia producida por la asignación. Esto supone un problema cuando la instancia de destino necesita esos valores. Para evitarlo, hay que establecer los valores necesarios explícitamente en la asignación. Puede establecer la **GenerateDefaultFixedNodes** indicador en **RequiredDefaults**, lo que significa que las necesarias nodos se tienen en cuenta. Esto cubre nodos vinculados, los valores de los nodos que han predeterminado, nodos con el **MinOccurs** propiedad establecida en mayor que o igual a uno y nodos cuyos elementos primarios son necesarios.  
  
> [!NOTE]
>  Después de establecer **GenerateDefaultFixedNodes** a **No** o **RequiredDefaults**, debe comprobar la asignación y comprobar que el resultado es el mismo que cuando  **GenerateDefaultFixedNodes** se establece en su valor predeterminado de **Sí**, en que todos los nodos se tienen en cuenta el compilador.  
  
## <a name="managing-for-each-usage-with-looping-conditional-and-value-mapping-functoids"></a>Administrar el uso de for-each con los functoids de condicional, Bucle y Asignación de valores  
 Cuando se usa un **bucle** functoid, un **condicional** functoid, o una **Value Mapping** functoid, un `xsl:for-each` instrucción se genera en la asignación compilada. Si el campo secundario del esquema de destino tiene un número máximo de apariciones sin enlazar, la instrucción `xsl:for-each` se inserta en el campo secundario. Si el campo secundario no tiene un número máximo de apariciones sin enlazar, la instrucción `xsl:for-each` se inserta en el campo primario de ese campo secundario.  
  
 Sin embargo, dado que la ubicación de la `xsl:for-each` instrucción afecta al resultado de la asignación, puede que desee la `xsl:for-each` instrucción se deben colocar en el campo secundario del esquema de destino, independientemente de si se establece el número máximo de apariciones del campo secundario a **1**.  
  
 Puede controlar la posición de la `xsl:for-each` instrucción modificando el valor de la **TreatElementsAsRecords** de atributo en el archivo de asignación (.btm) tal como se muestra:  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 Cuando este atributo se establece en **Sí**, `xsl:for-each` instrucción se coloca en el campo secundario del esquema de destino, independientemente de si el número máximo de apariciones del campo secundario está establecido en **1**.  
  
## <a name="preserving-the-order-when-mapping-a-repeating-sequence-group"></a>Conservar el orden al asignar un grupo de secuencias repetidas  
 Los grupos de secuencias de los esquemas XSD no proporcionan un contexto de bucle porque no están representados en la instancia de mensaje. Al no poder realizar bucles en el grupo de secuencias, el compilador del Asignador no genera el XSLT apropiado para mantener el orden de segmentos. Como resultado se pierde el contexto relativo presente en la instancia de entrada, lo que hace a las instancias de salida inútiles para procesamientos posteriores que dependan de dicho contexto relativo.  
  
 Puede usar el **PreserveSequenceOrder** marca para mantener el orden de los registros al asignar una repetición de secuencia a otra secuencia repetida. De forma predeterminada, el valor de la marca se establece en **No** para conservar la funcionalidad de las asignaciones existentes creadas en versiones anteriores [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] versiones donde la marca no está presente. En las nuevas asignaciones creadas, la marca estará presente con su valor establecido en **No**. Para mantener el orden de los segmentos, debe establecer explícitamente el valor en **Sí** en los archivos .btm, tal como se muestra:  
  
```  
<mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" TreatElementsAsRecords="No" OptimizeValueMapping="No" GenerateDefaultFixedNodes="Yes" PreserveSequenceOrder="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes">  
```  
  
 A continuación se da un ejemplo de instancia de entrada:  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
 Con el **PreserveSequenceOrder** marca establecida en **n**, la instancia de salida tendrá un aspecto similar al siguiente:  
  
```  
<Name>Person1</Name>  
<Name>Person2</Name>  
<Gender>Male</Gender>  
<Gender>Female</Gender>  
<Address>Bellevue</Address>  
<Address>Redmond</Address>  
```  
  
 Con el **PreserveSequenceOrder** marca establecida en **Sí**, la instancia de salida tendrá un aspecto similar al siguiente:  
  
```  
<Name>Person1</Name>  
<Gender>Male</Gender>  
<Address>Bellevue</Address>  
<Name>Person2</Name>  
<Gender>Female</Gender>  
<Address>Redmond</Address>  
```  
  
## <a name="see-also"></a>Vea también  
 [Crear asignaciones usando al asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)