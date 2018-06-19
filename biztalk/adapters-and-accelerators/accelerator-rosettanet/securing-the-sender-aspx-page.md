---
title: Protección de la página ASPX de remitente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ASPX pages, protocol rules
- security, ASPX pages
- RNIFSend.aspx
- ASPX pages, security
- protocol rules [ASPX pages]
ms.assetid: 8214e3f5-a8e9-4d71-957d-ed0852035030
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c5d5ec97d4d4aed862ffc1dbc0d75d0c0430d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207764"
---
# <a name="securing-the-sender-aspx-page"></a>Protección de la página ASPX de remitente
En este tema se describe cómo proteger la página RNIFSend.aspx del uso no autorizado. Hay dos procedimientos que puede usar:  
  
-   En el Administrador de Internet Information Services (IIS), proteja RNIFSend.aspx para asegurarse de que ningún servidor no autorizado utilizará la página RNIFSend.aspx para transmitir mensajes no autorizados de la red.  
  
-   Utilice Microsoft Internet Security and Acceleration (ISA) Server para crear una regla de protocolo de solicitudes HTTP salientes.  
  
### <a name="to-secure-rnifsendaspx"></a>Para proteger RNIFSend.aspx  
  
1.  En el servidor Web que se usa para la transmisión de mensajes RNIF, haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en  **Servicios de Internet Information Server (IIS) Manager**.  
  
2.  En el Administrador de IIS, expanda el nodo de equipo local, **sitios Web**y, a continuación, expanda **sitio Web predeterminado**.  
  
3.  Haga clic en **BTARNApp**y, a continuación, en el panel derecho, haga clic en **RNIFSend.aspx**.  
  
4.  Haga clic en **Propiedades**. En el **seguridad del archivo** ficha la **restricciones de nombre de dominio y dirección IP** sección, haga clic en **editar**.  
  
5.  En el cuadro de diálogo restricciones de nombre de dominio y dirección IP, haga clic en **acceso denegado**y, a continuación, haga clic en **agregar**.  
  
6.  En el **conceder acceso** cuadro de diálogo Agregar todos los servidores de BizTalk, operaciones de envío. Si agrega un solo servidor, haga clic en **único equipo**. En el **dirección IP** , escriba la dirección IP para el equipo y, a continuación, haga clic en **Aceptar**.  
  
7.  Si agrega un grupo de servidores, haga clic en **grupo de equipos**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Id. de red**|Tipo de la red que desea usar.|  
    |**Máscara de subred**|Escriba la máscara de subred que se va a utilizar.|  
  
8.  Haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si se han distribuido todas sus operaciones de envío a un host independiente que se ejecute en una instancia independiente, solamente debe agregar este equipo. Puede denegar todos los demás acceso.  
  
9. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
### <a name="to-create-a-protocol-rule-of-outgoing-http-requests"></a>Para crear una regla de protocolo de solicitudes HTTP salientes  
  
1.  En administración de ISA, haga clic en **directiva de acceso**y, a continuación, haga clic en **las reglas de protocolo**.  
  
2.  Crear una nueva regla de protocolo denominada **HTTP** que usa el protocolo TCP.  
  
3.  En la página de propiedades de su HTTP nueva regla, de protocolo en el **se aplica a** ficha, seleccione **se aplica a los conjuntos de direcciones de cliente especificadas a continuación**. Escriba solo esas direcciones IP que desea tener acceso a la página de cliente.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)