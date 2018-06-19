---
title: Publicar desde la consola de administración de BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbe03b1a8df67581ce73db31cd5ed4b80b7a109c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009101"
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a>Publicar desde la consola de administración de BizTalk Server
Si desea administrar el punto de conexión que se publica a través de la consola de administración de BizTalk Server en lugar del Portal de administración de ESB, puede hacerlo escribiendo un moniker de Universal Description, Discovery y Integration (UDDI) en el campo de descripción de los puntos de conexión Para publicar en UDDI. El siguiente es un moniker de ejemplo.  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 Puede establecer las siguientes propiedades UDDI mediante el **descripción** campo en la consola de administración de BizTalk Server:  
  
-   **ModifiedBy**. Esta propiedad opcional contiene el nombre de cuenta del usuario que modificó el punto de conexión; Por ejemplo, MyDomainName\MyUserName.  
  
-   **UDDIContact**. Esta propiedad opcional es el nombre de contacto del usuario definido para el proveedor de negocio de UDDI.  
  
-   **UDDIUserType**. Esta propiedad opcional es el tipo de usuario del usuario definido para el proveedor de negocio de UDDI.  
  
-   **UDDIEmail**. Esta propiedad opcional es la dirección de correo electrónico del usuario definido para el proveedor de negocio de UDDI.  
  
-   **TransportType**. Esta propiedad opcional es el tipo de adaptador de punto de conexión, como **archivo, MQS, WCF-WsHttp, SOAP, HTTP,** o **FTP**.  
  
-   **Estado**. Esta propiedad opcional es el estado del punto de conexión, como **publicada** o **pendiente**. El servicio de publicación de UDDI usa este atributo para detectar el estado del punto de conexión.  
  
-   **BindingType**. Esta propiedad opcional es el protocolo específico (tipo de dirección URL) que admite el enlace de UDDI, como **mailto, http, https, ftp, fax, teléfono,** o **otros**. El servicio de publicación de UDDI usa este atributo para crear el enlace de punto de conexión.