---
title: Configurar el contexto de la aplicación mediante las propiedades de contexto de mensaje en Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b76788-5c81-4bb4-8ef6-b1439955ea97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71920920c11028adb1f699e3faee463876399b36
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004005"
---
# <a name="configure-the-application-context-using-message-context-properties-in-oracle-e-business-suite"></a>Configurar el contexto de la aplicación mediante las propiedades de contexto de mensaje en Oracle E-Business Suite
Para realizar operaciones en los artefactos de Oracle E-Business Suite mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe establecer el contexto de la aplicación de forma adecuada. Puede establecer el contexto de la aplicación de las maneras siguientes:  
  
- Mediante la especificación de las propiedades de enlace que expone el adaptador. Para obtener más información, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
- Mediante el uso de las propiedades de contexto de mensaje que expone el adaptador. Debe tener en cuenta lo siguiente al establecer el contexto de la aplicación mediante el uso de las propiedades de contexto de mensaje.  
  
  -   Puede establecer los valores solo para **ApplicationShortName**, **OrganizationID**, **ResponsibilityKey**, y **ResponsibilityName** mediante el uso de propiedades de contexto del mensaje. El nombre de usuario y contraseña, debe usar las propiedades de enlace. El valor especificado para el **ResponsibilityKey** propiedad de contexto de mensaje invalida el valor especificado para el **ResponsibilityName** propiedad de contexto del mensaje.  
  
  -   Si establece el contexto de la aplicación mediante las propiedades de enlace y las propiedades de contexto de mensaje, los valores especificados para las propiedades de contexto de mensaje tienen prioridad e invalidan los valores especificados para las propiedades de enlace. Sin embargo, por ejemplo, si especifica el nombre corto de la aplicación como una propiedad de contexto de mensaje y el nombre de identificador y la responsabilidad de la organización como propiedades de enlace, solo el valor para el nombre corto de la aplicación procede de la propiedad de contexto de mensaje. El resto se toman de las propiedades de enlace correspondientes.  
  
  ¿Por qué usar propiedades de contexto de mensaje a través de propiedades para establecer el contexto de la aplicación de enlace? Si establece el contexto de la aplicación mediante las propiedades de enlace, el WCF-Custom puerto de envío el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] puede usarse solo para el Id. de organización específica, la responsabilidad y la aplicación que ha especificado para las propiedades de enlace. Por el contrario, si usa la propiedad de contexto de mensaje, puede configurar un puerto de envío WCF-Custom "genérico" y establecer el contexto de la aplicación en el nivel de mensaje.  
  
  Los clientes del adaptador deben establecer las propiedades de contexto del mensaje en el mensaje que se envía a Oracle E-Business Suite para invocar una operación en Oracle E-Business Suite. Los mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] son inmutables. Por lo tanto, los clientes deben crear primero un mensaje del mensaje existente y, a continuación, establezca el mensaje de las propiedades de contexto en el nuevo mensaje. El procedimiento descrito en esta sección, se supone que el mensaje existente se denomina **solicitar**, y el nuevo mensaje se denomina **New_Request**.  
  
## <a name="set-the-message-context-properties-for-biztalk-applications"></a>Establecer el mensaje de propiedades de contexto para las aplicaciones de BizTalk  
  
1. Abra el proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
2. En el Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **agregar referencias**.  
  
3. En el **Agregar referencia** cuadro de diálogo, haga clic en el **examinar** pestaña y, a continuación, vaya a la ubicación donde el esquema de propiedades de BizTalk DLL para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] está disponible.  
  
    Este archivo DLL, `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`, se instala de forma el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en \< *unidad de instalación*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin.  
  
4. Seleccione el archivo DLL y, a continuación, haga clic en **agregar**.  
  
5. En la orquestación de BizTalk, agregue un mensaje, **New_Request**. Para el **tipo de mensaje** propiedad, asegúrese de seleccionar el mismo tipo que el mensaje de solicitud existente.  
  
6. Antes de la forma de envío con que se envía el mensaje al puerto de envío, agregue una forma construir mensaje y dentro de ella, una forma asignación de mensajes.  
  
7. Haga doble clic en la forma asignación de mensajes para abrir **Editor de expresiones de BizTalk**.  
  
8. En **Editor de expresiones de BizTalk**, agregue lo siguiente y, a continuación, haga clic en **Aceptar**:  
  
   ```  
   New_Request = Request;  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ApplicationShortName) = "AR";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityKey) = "RECEIVABLES_VISION_OPERATIONS";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityName) = "Receivables, Vision Operations (USA)";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.OrganizationId) = "204";  
   ```  
  
   > [!IMPORTANT]
   >  El valor especificado para el **ResponsibilityKey** propiedad de contexto de mensaje invalida el valor especificado para el **ResponsibilityName** propiedad de contexto del mensaje.  
  
9. Asegúrese de que el procesamiento posterior de la orquestación se realiza mediante el **New_Request** mensaje.  
  
10. Antes de implementar esta orquestación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe agregar la referencia de ensamblado para `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll` en la aplicación de BizTalk donde va a implementar la orquestación. Para implementar un ensamblado en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:  
  
    1. Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
    2. En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, la aplicación a la que desea agregar un ensamblado de BizTalk.  
  
    3. Los clientes del adaptador no reciben la respuesta de SAP  
  
    4. En el **agregar recursos** cuadro de diálogo, haga clic en **agregar**, navegue hasta la carpeta que contiene el archivo de ensamblado de BizTalk, que es \< *unidad de instalación* \>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin. Seleccione el `Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll` de archivo y, a continuación, haga clic en **abierto**.  
  
    5. En el **opciones** ficha, especifique las opciones para instalar el ensamblado de BizTalk a la caché de ensamblados global (GAC) y, a continuación, haga clic en **Aceptar**.  
  
## <a name="set-the-language-for-performing-operations"></a>Establecer el idioma para realizar operaciones  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con la característica de compatibilidad con varios idiomas (MLS) de Oracle E-Business Suite, y le permite especificar un idioma al realizar las operaciones. Expone el adaptador el **lenguaje** propiedad de contexto para especificar un idioma para realizar operaciones de mensaje.  
  
 El valor especificado para el **lenguaje** propiedad de contexto de mensaje invalida el valor de la **lenguaje** enlaza la propiedad en el **MlsSettings** enlaza la propiedad. Para obtener más información sobre la **MlsSettings** enlaza la propiedad, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
