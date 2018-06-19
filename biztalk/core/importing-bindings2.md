---
title: Importar Bindings2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings, requirements
- importing, bindings
- bindings, importing
ms.assetid: 9e10bc04-aba8-430a-b8fd-de9399d54f88
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f2c92d5469f88494c77ad062d97c53768572a5b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006133"
---
# <a name="importing-bindings"></a>Importar enlaces
En los temas de esta sección se describe cómo importar enlaces a un grupo o a una aplicación de BizTalk.  
  
 Al importar enlaces, tenga en cuenta los siguientes puntos importantes:  
  
-   **Los enlaces existentes se sobrescribirán.** Si los enlaces que vaya a importar tiene el mismo nombre que enlaces ya existentes, éstos se sobrescribirán. Además, si el archivo de enlace contiene entidades y alias, los enlaces para entidades y alias con el mismo nombre que ya existan en la aplicación se sobrescribirán.  
  
-   **Todos los enlaces de un grupo deben ser únicos.** Si un enlace que tiene el mismo nombre que uno que está importando ya existe en el grupo, se producirá un error en la operación de importación.  
  
-   **Debe volver a configurar las contraseñas.** Por motivos de seguridad, cuando exporte un archivo de enlace, BizTalk Server quita las contraseñas de los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la consola de administración de BizTalk Server para el puerto de envío o la ubicación de recepción. Para obtener instrucciones, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Vea también [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
-   **El host debe existir en el grupo.** Un host correspondiente al especificado en los enlaces debe existir en el grupo de BizTalk en el que se están importando los enlaces; además, el nivel de confianza del host debe coincidir. De lo contrario, se producirá un error en la operación de importación.  
  
-   **Comportamiento de la importación de enlace depende del origen de los enlaces.** Los enlaces se pueden haber exportado de un ensamblado, una aplicación o un grupo. En función de la ubicación desde la que se exportaron los enlaces, la operación de importación puede tener efectos diferentes, como se muestra en la tabla siguiente:  
  
    |Origen de los enlaces|Importar a una aplicación|Importar a un grupo|  
    |----------------------------|-----------------------------------|----------------------------|  
    |Enlaces exportados de un ensamblado|La aplicación especificada debe contener un ensamblado que tenga el mismo nombre que el ensamblado desde el que se exportó el archivo de enlace. De lo contrario, se produce un error en la operación de importación.|El grupo debe contener un ensamblado y una aplicación que tengan el mismo nombre que el ensamblado y la aplicación desde los que se exportó el archivo de enlace. De lo contrario, se produce un error en la importación.|  
    |Enlaces exportados de una aplicación|La aplicación desde la que se exportó el archivo de enlace debe tener el mismo nombre que la aplicación especificada. De lo contrario, se produce un error en la operación de importación.|La aplicación desde la que se exportó el archivo de enlace debe tener el mismo nombre que una aplicación del grupo al que se importan los enlaces. De lo contrario, se produce un error en la operación de importación.|  
    |Enlaces exportados de un grupo|El grupo desde el que se exportó el archivo de enlace debe incluir una aplicación que tenga el mismo nombre que la aplicación especificada. De lo contrario, se produce un error en la operación de importación.|Los enlaces se importan para las aplicaciones correspondientes. En otras palabras, los enlaces de una aplicación del grupo desde el que se exportaron los enlaces se importan a una aplicación que tiene el mismo nombre en el grupo actual.|  
  
-   **El atributo de nombre de un adaptador puede ser incorrecto.** Si el archivo de enlace incluye la configuración de un adaptador, compruebe que el atributo Name del elemento TransportType del archivo de enlace es el mismo que el configurado para el adaptador en la consola de administración de BizTalk Server (en configuración de plataforma > adaptadores).  
  
     En concreto, debe comprobar si éste es el caso al importar enlaces desde [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] a BizTalk Server. Algunos transportes para los que esto podría resultar un problema son los siguientes:  
  
    -   MQS  
  
    -   MSMQ  
  
    -   POP3  
  
    -   Windows SharePoint Services  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo importar enlaces a un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md)  
  
-   [Cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md)  
  
-   [Cómo importar enlaces para una solución EDI y AS2](../core/how-to-import-bindings-for-an-edi-as2-solution.md)