---
title: Personalización de enumeraciones en el esquema de sobres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b053d82-753f-4a05-9922-fa5dbd073ba9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8897130974f0d2248de49d2fd84646bb0cbafd7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991997"
---
# <a name="customizing-enumerations-in-the-envelope-schema"></a>Personalizar enumeraciones en el esquema de sobres
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite personalizar las enumeraciones de campo de identificador en el esquema de servicio (sobre). Esto le permite recibir o enviar intercambios que tengan valores que no sean estándar (que estén fuera del conjunto de valores definidos por el organismo de estándares de X12) en los campos de Id. de remitente o de receptor del sobre. También permite cambiar los calificadores disponibles en las listas desplegables para los valores de encabezado en definiciones de propiedades de acuerdo.  
  
> [!IMPORTANT]
>  Cuando se modifica un esquema, se aplica la misma modificación para todas las transacciones del estándar en cuestión. No se puede realizar una modificación en el esquema de sobres para una única entidad.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] extrae la lista de valores permitidos de los esquemas de servicio estáticos de Microsoft.BizTalk.Edi.BaseArtifacts.dll, que se suministra con el producto. Para ampliar el conjunto de valores base, debe desarrollar e implementar una extensión de esquema de servicio. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proporciona el servicio (sobre) plantillas de esquemas que puede usar para modificar las enumeraciones. Estos esquemas de servicio son X12_ServiceSchemaExtension.xsd y EDIFACT_ServiceSchemaExtension.xsd. Cada esquema personalizado tendrá uno de los siguientes espacios de nombres, en función del estándar. Este espacio de nombres no puede modificarse.  
  
|Estándar|Espacio de nombres|  
|--------------|---------------|  
|X12 y HIPAA|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006`|  
|EDIFACT|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`|  
  
 Realice los cambios en el esquema en el Editor de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] (vea el siguiente procedimiento). Una vez realizados estos cambios necesarios, debe implementar el esquema.  
  
 Tanto para la recepción como para el envío, cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] valida los segmentos de sobre (ISA y GS para X12, o UNB y UNG para EDIFACT), comprobará la existencia del esquema de servicio personalizado en función de su espacio de nombres. Si se ha implementado el esquema personalizado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lo combinará con el esquema de servicio habitual, y usará tanto los valores de enumeración personalizados como los estándar cuando se especifique. Puede personalizar el esquema para ampliar una lista de enumeraciones, pero no puede quitarle valores. Si no se ha implementado ningún esquema personalizado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará el esquema de servicio estándar.  
  
 Una vez implementado un esquema personalizado, la interfaz de usuario de [!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará los valores de una enumeración personalizada para rellenar las listas desplegables correspondientes de las páginas de propiedades de [!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)]. Si no se ha implementado ningún esquema personalizado, [!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)] usará los valores de las enumeraciones del esquema de servicio estándar. Además, el tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará la enumeración personalizada para validar un mensaje.  
  
 Si usa las herramientas de XML proporcionadas con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para validar una instancia con su sobre y ha personalizado el esquema de servicios, deberá incluir el esquema de servicio personalizado en el proyecto de BizTalk, además de los esquemas de documento (conjunto de transacciones) y, si fuera necesario, el esquema por lotes. Esto no es necesario si va a validar una instancia de conjuntos de transacciones que no tiene sobre.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
##  <a name="BKMK_Env_Can"></a> Campos de sobre que pueden modificarse  
 Sólo pueden modificarse los siguientes campos de sobre. Sólo se incluyen estos campos en los esquemas de extensiones. La agregación de otros campos en el esquema de extensión de servicio no tendrá ningún efecto en el procesamiento.  
  
|Estándar|Campo|  
|--------------|-----------|  
|X12 y HIPAA|ISA01: calificador de autorización<br /><br /> ISA03: calificador de seguridad<br /><br /> ISA05: calificador Id. de remitente<br /><br /> ISA07: calificador de Id. de receptor<br /><br /> GS01: código funcional<br /><br /> GS07: agencia responsable|  
|EDIFACT|UNB2.2: calificador de código de remitente<br /><br /> UNB3.2: calificador de código de receptor|  
  
## <a name="envelope-fields-that-should-not-be-modified"></a>Campos de sobre que no deben modificarse  
 Algunos campos del sobre generan comportamientos en el motor. Como resultado, no debe agregar valores a la lista de enumeraciones existente para cualquiera de estos campos. Estos campos son los siguientes:  
  
|Estándar|Campo|  
|--------------|-----------|  
|X12 y HIPAA|ISA11: identificador de estándares de control de intercambio<br /><br /> ISA12: número de versión de control de intercambio<br /><br /> ISA14: confirmación solicitada|  
|EDIFACT|UNB 1.1: identificador de sintaxis<br /><br /> UNB 1.2: número de versión de sintaxis<br /><br /> UNB9: solicitud de confirmación|  
  
### <a name="to-customize-an-enumeration-in-the-envelope-schema"></a>Para personalizar una enumeración en el esquema de sobres  
  
1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree un proyecto nuevo.  
  
2. Editor de BizTalkm agregue el esquema X12_ServiceSchemaExtension.xsd (para modificar enumeraciones de X12 o HIPAA) o el esquema EDIFACT_ServiceSchemaExtension.xsd en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI para un proyecto BizTalk. Abra el esquema.  
  
3. Para cambiar los valores de enumeración, seleccione la enumeración en el **propiedades** panel y, a continuación, haga clic en el botón de puntos suspensivos para abrir el **Editor de enumeración**. Agregar a la lista de valores, según sea necesario, lo que garantiza que hay un valor en cada línea en el **valores** panel. Haga clic en **Aceptar**.  
  
   > [!IMPORTANT]
   >  No puede cambiar el espacio de nombres del esquema de servicio. El esquema debe tener el mismo espacio de nombres y el mismo nombre de nodo raíz que el esquema de extensión original instalado con el producto.  
  
   > [!NOTE]
   >  Si agrega un campo nuevo a los esquemas, ese campo se ignorará. Solo los campos enumerados en la [sobre los campos que pueden modificarse](../core/customizing-enumerations-in-the-envelope-schema.md#BKMK_Env_Can) se puede cambiar la sección anterior.  
  
4. Guarde el esquema.  
  
5. Haga clic en el esquema y haga clic en **implementar**.  
  
   > [!NOTE]
   >  El esquema debe implementarse en el grupo actual de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de esquemas EDI](../core/developing-edi-schemas.md)   
 [Modificación de esquemas EDI](../core/modifying-edi-schemas.md)