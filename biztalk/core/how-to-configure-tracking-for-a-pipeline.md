---
title: Habilitar el seguimiento de canalizaciones | Documentos de Microsoft
description: "Realizar un seguimiento de cuerpos de mensaje y eventos cuando la canalización procesa los mensajes en BizTalk Server"
ms.custom: 
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed836947ff47e21eeeb3bc306e94ea08f5464f0
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/13/2017
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a>Configurar la canalización de seguimiento de BizTalk Server
Use la administración de BizTalk Server para configurar el seguimiento de una canalización. Puede que desee configurar el seguimiento con fines de solución de problemas y auditoría. Puede ver propiedades de mensajes, eventos de puerto y eventos de mensajes. También puede realizar un seguimiento de eventos de mensaje y eventos de puerto para mensajes.  
  
 Puede configurar el seguimiento de una de las canalizaciones predeterminadas incluidas en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], o bien de una canalización personalizada que se haya implementado en una aplicación de BizTalk. Los parámetros de seguimiento que haya definido se aplicarán a todas las instancias de la canalización.  
  
> [!IMPORTANT]
>  Aunque puede configurar el seguimiento de una canalización, esto genera una gran cantidad de datos porque los datos se recopilan globalmente para todos los puertos que utilizan la canalización. En su lugar, recomendamos que configurar el seguimiento de su envío y puertos de recepción, como se describe en [configurar seguimiento para un puerto de envío](../core/how-to-configure-tracking-for-a-send-port.md) y [configurar seguimiento para un puerto de recepción](../core/how-to-configure-tracking-for-a-receive-port.md).  
  
 Para obtener más información acerca de la instancia de servicio y eventos de mensaje seguimiento características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [ver realiza el seguimiento de mensajes y datos de instancia](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>Prerequisites  
Inicie sesión con una cuenta que sea miembro del grupo Administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="enable-pipeline-tracking"></a>Habilitar el seguimiento de canalización
  
1.  En **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la canalización. 
  
2.  Realice una de las siguientes operaciones:  
  
    -   Para configurar el seguimiento para una de manera predeterminada las canalizaciones de BizTalk, expanda \<todos los artefactos\>.  
  
    -   Para configurar el seguimiento para una canalización personalizada que se ha implementado en una aplicación de BizTalk, expanda la aplicación que contiene la canalización.  
  
3.  Seleccione el **canalizaciones** carpeta, haga clic en la canalización y, a continuación, seleccione **seguimiento**.  
  
    > [!NOTE]
    >  Para configurar el seguimiento de varias canalizaciones a la vez, mantenga presionada la tecla MAYÚS y seleccione cada canalización para configurar, haga clic en una de las canalizaciones y, a continuación, seleccione **seguimiento**.  
  
4.  Utilice los detalles siguientes para configurar las opciones de seguimiento que desee y, a continuación, seleccione **Aceptar** para guardar los cambios.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Seguimiento de eventos - puerto de inicio y finalización de eventos**|Realiza un seguimiento sólo cuando se inicia y finaliza una instancia. Los detalles incluyen el nombre de elemento, el ensamblado y otros metadatos.|  
    |**Seguimiento de eventos - envío de mensaje y recibir eventos**|Realiza un seguimiento de envío y recepción de mensajes eventos. Sólo está disponible si **eventos de inicio y fin de puerto** está seleccionada.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensajes antes del procesamiento de canalización**|Guarda y realiza un seguimiento de los cuerpos de mensaje recibidos por la canalización, que contiene metadatos tales como las direcciones URL y las propiedades promocionadas. Si se trata de una canalización de recepción, el cuerpo del mensaje es el mensaje sin procesar que envía el componente de transporte a la canalización. En función de la aplicación, el mensaje podría estar cifrado, firmado o codificado. Al utilizar una asignación de BizTalk, si se trata de una canalización de recepción, el seguimiento se efectúa después de que se procese la asignación de entrada.<br /><br /> Sólo está disponible si **envío de mensajes y recibir eventos** está seleccionada.|  
    |**Realizar un seguimiento de cuerpos de mensaje - mensajes después del procesamiento de canalización**|Guarda y realiza un seguimiento de los cuerpos de mensaje enviados por la canalización, que contiene metadatos tales como las direcciones URL y las propiedades promocionadas. Si se trata de una canalización de recepción, el cuerpo del mensaje es el mensaje procesado que se va a enviar a la base de datos de cuadro de mensajes, que puede ser XML, según la aplicación que utilice. Al utilizar una asignación de BizTalk, si se trata de una canalización de envío, el seguimiento se efectúa antes de que se procese la asignación de salida.<br /><br /> Sólo está disponible si **envío de mensajes y recibir eventos** está seleccionada.|  
  
## <a name="see-also"></a>Vea también  
 [Administración de canalizaciones](../core/managing-pipelines.md)
