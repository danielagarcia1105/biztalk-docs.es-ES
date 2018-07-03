---
title: Modificación de esquemas 2.XML para trabajar con el Editor de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, modifying
- modifying, 2.XML schemas
ms.assetid: 07316826-84b6-494e-81b9-f64a3d46ffb0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96dd1c4cd8909564ff39c78b5b1a9e4fc248d93f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972861"
---
# <a name="modifying-2xml-schemas-to-work-with-biztalk-editor"></a>Modificación de esquemas 2.XML para trabajar con el Editor de BizTalk
Esquemas de HL7 2.XML requieren ninguna modificación para funcionar correctamente con el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]). El siguiente describe cómo modificar HL7 V2. Esquemas XML para que pueda usarlos con el Editor de BizTalk.  
  
> [!IMPORTANT]
>  La herramienta Update2XMLSchema realiza estos pasos automáticamente. Consulte [herramienta Update2XMLSchema](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md) para obtener más información.  
> 
> [!NOTE]
>  El **nillable** atributo puede aparecer en un esquema en un elemento. Si establece en **true**, indica que la instancia del elemento primario puede tener un **xsi: nil = "true"** atributo. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] omite este atributo durante la compilación y durante el análisis y serialización.  
  
### <a name="to-modify-2xml-schemas"></a>Para modificar esquemas 2.Xml  
  
1. En el archivo fields.xsd, debe quitar las instancias de **importar** y reemplácelas con **incluyen**. Por ejemplo, busque el archivo fields.xsd el texto siguiente:  
  
   ```  
   <xsd:import namespace="urn:hl7-org:v2xml" schemaLocation="datatypes.xsd"/>   
   ```  
  
    Y cambie el texto a lo siguiente:  
  
   ```  
   <xsd:include schemaLocation="datatypes.xsd"/>   
   ```  
  
2. En el archivo segments.xsd, debe quitar todas las instancias de las líneas que contienen texto processContents = "lax". Por ejemplo, busque el archivo segments.xsd el texto siguiente:  
  
   ```  
   <xsd:any processContents="lax" namespace="##any" minOccurs="0"/>   
   ```  
  
    And  
  
   ```  
   <xsd:any processContents="lax" namespace="##any"/>   
   ```  
  
    Y quite estas líneas.  
  
3. Para todos los esquemas, en la etiqueta de XSD: Schema, debe agregar la siguiente línea:  
  
   > [!NOTE]
   >  No agregue esta línea si ha agregado el esquema mediante Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] porque [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] hace esto automáticamente.  
  
   ```  
   xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
   ```  
  
    Por ejemplo, en el archivo ADT_A01.xsd, busque el texto siguiente:  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="urn:hl7-org:v2xml"   
    targetNamespace="urn:hl7-org:v2xml">   
   ```  
  
    Y cambie el texto a lo siguiente:  
  
   ```  
   <xsd:schema  
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
    xmlns="urn:hl7-org:v2xml"  
    targetNamespace="urn:hl7-org:v2xml"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003">   
   ```  
  
4. Para todos los esquemas, debe agregar una referencia de raíz. Por ejemplo, en el archivo ADT_A01.xsd, busque el texto siguiente:  
  
   ```  
   <xsd:include schemaLocation="segments.xsd" />   
   ```  
  
    Y cambie el texto para:  
  
   ```  
   <xsd:include schemaLocation="segments.xsd" />  
   <xsd:annotation>   
     <xsd:appinfo>   
       <schemaInfo root_reference="ADT_A01"  
    xmlns="http://schemas.microsoft.com/BizTalk/2003" />   
     </xsd:appinfo>   
   </xsd:annotation>   
   ```  
  
   > [!NOTE]
   >  Si usas [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], puede agregar este root_reference mediante el procedimiento siguiente.  
  
### <a name="to-add-the-root-reference"></a>Para agregar la referencia raíz  
  
1.  En el Explorador de soluciones, haga doble clic en el esquema que desea editar.  
  
2.  En el panel Propiedades, desplácese a la propiedad **root_reference**y en la lista desplegable, haga clic en la propiedad con el mismo nombre de esquema.  
  
3.  En el menú **Archivo** , haga clic en **Guardar todo**.  
  
## <a name="see-also"></a>Vea también  
 [Uso de esquemas de HL7 2.XML](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)