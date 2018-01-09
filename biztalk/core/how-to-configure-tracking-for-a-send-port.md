---
title: "Habilitar el seguimiento en un puerto de envío | Documentos de Microsoft"
description: "Activar el seguimiento de cuerpos de mensaje y realizar el seguimiento de propiedades de mensaje en un puerto de envío de BizTalk Server"
ms.custom: 
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f32e97b0-244c-4acc-8f3f-b18cdb9ec0da
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 223c417769086cc71f501b044410bf2d3e4cbc74
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2017
---
# <a name="configure-send-port-tracking-in-biztalk-server"></a>Configurar el seguimiento de puerto de envío de BizTalk Server
Use la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para configurar el seguimiento de un puerto de envío, tales como las opciones para ver los cuerpos de mensajes y las propiedades promocionan. Esto le ayuda supervisar el estado de su implementación de BizTalk e identificar cualquier cuello de botella. La configuración de seguimiento que haya definido se aplicará a todas las instancias del puerto de envío.  
  
 Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>Prerequisites  
Inicie sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. Para obtener más información acerca de los permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="enable-tracking-on-a-send-port"></a>Habilitar el seguimiento en un puerto de envío  
  
1.  En **administración de BizTalk Server**, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk que tiene el puerto de envío.  
  
2.  Seleccione **puertos de envío**, haga clic en el puerto de envío, seleccione **propiedades**y, a continuación, seleccione **seguimiento**.  
  
    > [!NOTE]
    >  Un puerto de envío solo se puede asociar a una canalización de envío. Si se deshabilitan el seguimiento de cuerpos de mensaje en la canalización de envío, a continuación, nada se realiza un seguimiento del puerto de envío. En un escenario como este, puede deshabilitar las opciones de "Seguimiento" en ese puerto de envío.  
  
3.  Utilice los detalles siguientes para habilitar las opciones de seguimiento que desee y, a continuación, seleccione **Aceptar** para guardar los cambios.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud antes de procesamiento de puerto**|Guarda y realiza un seguimiento de contenido del mensaje antes de que se recibe el mensaje. <br/><br/> **Tenga en cuenta**: asegúrese de habilitar el seguimiento de canalización partes de mensaje realizar el seguimiento correctamente el mensaje de respuesta antes de procesamiento de puerto.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensaje de solicitud después del procesamiento de puerto**|Guarda y realiza un seguimiento de contenido del mensaje una vez recibido el mensaje.|  
    |**Realizar un seguimiento de cuerpos de mensaje – mensaje de respuesta antes de procesamiento de puerto**|Guarda y realiza un seguimiento de contenido del mensaje antes de enviar el mensaje. Solo está disponible para los puertos de envío de petición-respuesta.|    
    |**Realizar un seguimiento de cuerpos de mensaje – mensaje de respuesta después del procesamiento de puerto**|Guarda y realiza un seguimiento de contenido del mensaje después de que se envía el mensaje. Solo está disponible para los puertos de envío de petición-respuesta.|  
    |**Realizar un seguimiento de cuerpos de mensaje – mensaje de respuesta después del procesamiento de puerto**|Realiza un seguimiento de las propiedades promocionadas de un mensaje entrante.|  
    |**Seguimiento de propiedades de mensaje - mensaje de solicitud después del procesamiento de puerto**|Realiza un seguimiento de las propiedades promocionadas de un mensaje saliente.|  
    |**Seguimiento de propiedades de mensaje – mensaje de respuesta antes de procesamiento de puerto**|Guarda y realiza el seguimiento de propiedades del mensaje antes de enviar el mensaje. Solo está disponible para los puertos de envío de petición-respuesta.|   
    |**Seguimiento de propiedades de mensaje – mensaje de respuesta después del procesamiento de puerto**|Guarda y realiza el seguimiento de propiedades después de enviar el mensaje. Solo está disponible para los puertos de envío de petición-respuesta.|   
  
## <a name="see-also"></a>Vea también  
 [Creación y configuración de puertos de envío](../core/creating-and-configuring-send-ports.md)
