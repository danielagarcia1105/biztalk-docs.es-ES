---
title: Cómo importar enlaces para una solución EDI AS2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b918fa2-44f2-4f57-95af-36858cea0d86
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c25f3837d6eb0c938900b0da9e34246f1c6038
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007597"
---
# <a name="how-to-import-bindings-for-an-edi-as2-solution"></a>Cómo importar enlaces para una solución EDI y AS2
En este tema se describe cómo importar la configuración de una solución EDI y/o AS2 en otro equipo. La implementación de una solución EDI y AS2 se integra con la implementación de aplicaciones de BizTalk. Está disponible a través de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y la herramienta de línea de comandos BTSTask.  
  
 Puede importar la configuración de un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] mediante el uso de un archivo de enlace creado en el equipo de origen con la exportación de los enlaces correspondientes. Para obtener información acerca de cómo exportar una configuración en un archivo de enlace, vea [cómo exportar enlaces para una solución EDI AS2](../core/how-to-export-bindings-for-an-edi-as2-solution.md). Para obtener información acerca de un archivo de enlace creado a partir de una configuración, consulte [estructura de un archivo de enlace](../core/structure-of-a-binding-file.md).  
  
 También puede importar enlaces como parte de la importación de una aplicación mediante un archivo .msi. Para obtener más información, consulte el [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). También puede utilizar el comando BTSTask para exportar e importar enlaces. Para obtener más información acerca de BTSTask, vea el [referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md) tema en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe haber iniciado sesión con una cuenta que sea miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
-   Debe haber agregado una referencia a la **aplicación EDI de BizTalk** desde una aplicación de BizTalk que se usará como una aplicación de EDI. Para obtener instrucciones sobre cómo agregar una referencia a la aplicación EDI de BizTalk, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  
  
## <a name="importing-bindings"></a>Importar enlaces  
 Al importar una configuración, las propiedades de EDI existentes se sobrescribirán. Si va a importar propiedades para una entidad que tiene el mismo nombre que otra entidad existente, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] invalidará las propiedades de EDI (o los enlaces) para la entidad existente. Además, si va a importar propiedades globales de EDI, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sobrescribirá las propiedades globales de EDI existentes.  
  
 Tras importar una configuración, debe volver a configurar las contraseñas. Por motivos de seguridad, cuando se exporta un archivo de enlace [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] quita las contraseñas de los enlaces del archivo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Quita los campos UNB6.1 y UNB6.2 de las propiedades de EDIFACT y los campos ISA1, ISA2, ISA3 y ISA4 del X12 propiedades. Tras importar los enlaces, debe volver a configurar estos campos confidenciales antes de procesar los mensajes EDI.  
  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede importar un conjunto de enlaces, esto puede deberse a que la propiedad de host de confianza del archivo de enlace es diferente de la propiedad de autenticación de confianza para el host. Puede solucionar este problema cambiando la propiedad de host de confianza en el archivo de enlace.  
  
> [!NOTE]
>  Importar un archivo de enlace de las versiones anteriores de BizTalk Server a BizTalk Server puede producir un error. Dado que el modelo de administración de socios ha cambiado considerablemente para BizTalk Server, importar un archivo de enlace de versiones anteriores de BizTalk Server no puede crear las entidades en BizTalk Server de acuerdo con el nuevo modelo. Para obtener más información, consulte [¿cómo definiciones de entidades de traducir de versiones de servidor de BizTalk anterior en las nuevas entidades TPM?](../core/how-to-import-bindings-for-an-edi-as2-solution.md#BKMK_Party).  
  
### <a name="to-import-the-configuration-from-a-binding-file"></a>Para importar la configuración de un archivo de enlace  
  
1.  En el equipo en el que desee importar la configuración, abra la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
2.  Haga clic en la aplicación de BizTalk que desea importar la configuración de EDI y AS2, seleccione **importar**y, a continuación, haga clic en **enlaces**.  
  
3.  En el cuadro de diálogo Importar enlaces, desplácese a la ubicación que contiene el archivo de enlace y, a continuación, haga clic en **abiertos**.  
  
4.  Después de importar los enlaces, abra la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Configure de forma manual todos los campos de contraseña de EDI con los valores correspondientes.  
  
##  <a name="BKMK_Party"></a>¿Cómo definiciones de entidades de traducir de versiones de servidor de BizTalk anterior en las nuevas entidades TPM?  
 En BizTalk Server, una definición de entidad es básicamente un acuerdo que define cómo se intercambian los mensajes entre dos socios comerciales. En BizTalk Server, EDI y AS2 de mensajería se ha sometido a una gran cantidad de cambio y el nuevo modelo de administración de socios comerciales (TPM) ahora requiere acuerdos que se pueden crear entre dos perfiles de socios comerciales. Por lo tanto, para que exista un acuerdo, se deben haber definido primero los dos socios comerciales, los perfiles para cada uno de ellos y la configuración de protocolo para ambos perfiles de socios comerciales. Una vez definidas estas entidades, puede crear un acuerdo entre socios comerciales.  
  
> [!NOTE]
>  Para obtener más información relacionada con las mejoras de TPM en BizTalk Server, vea [bloques de creación de una solución de administración de socios comerciales](../core/building-blocks-of-a-trading-partner-management-solution.md).  
  
 ¿Dado el nuevo modelo de objetos TPM, esto significa que no se pueden migrar las aplicaciones EDI que creó en el servidor BizTalk Server a BizTalk Server? La respuesta es no. Puede volver a usar las aplicaciones existentes de BizTalk Server 2006 R2 o BizTalk Server 2009 en BizTalk Server mediante el uso de la herramienta de migración de entidades para migrar los datos de entidades de versiones anteriores de BizTalk Server. Para obtener más información acerca de la herramienta, consulte [migrar artefactos de EDI desde una versión anterior de BizTalk Server](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c).  
  
## <a name="see-also"></a>Vea también  
 [Importación de enlaces](../core/importing-bindings2.md)