---
title: Cómo configurar un puerto de envío MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send ports
- send ports, MSMQ adapters
- configuring [MSMQ adapters], send ports
ms.assetid: 37313d45-8148-4aaf-a3f2-ea05b3b8b448
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aad4a63a11f415c57778db726af0559858eab05c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992021"
---
# <a name="how-to-configure-an-msmq-send-port"></a>Cómo configurar un puerto de envío MSMQ
Se pueden establecer variables del adaptador de puerto de envío MSMQ en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si no se establecen las propiedades para el puerto de envío, se usarán los valores predeterminados del controlador de envío establecidos en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

> [!IMPORTANT]
>  Si una instancia de host está asociada con una ubicación de recepción o un puerto de envío MSMQ, compruebe que el servicio MSMQ se está ejecutando en ese equipo. Si el servicio no está en ejecución, los puertos de recepción MSMQ se cerrarán poco después de que se inicien y se suspenderán los mensajes enviados a los puertos de envío MSMQ.  
>   
>  En un escenario agrupado, es necesario que tanto la instancia de MSMQ agrupada como el servicio MSMQ de cada uno de los equipos del clúster esté en ejecución.  

## <a name="to-configure-variables-for-an-msmq-send-port"></a>Para configurar variables para un puerto de envío MSMQ  
 Siga estos pasos para configurar variables para un puerto de envío MSMQ:  

1. En la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cree un nuevo puerto de envío o haga doble clic en uno existente para modificarlo. Consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md) para obtener más información. Configure todas las opciones del puerto de envío. En el **General** ficha la **transporte** , especifique **MSMQ** para el **tipo** opción.  

2. En el **General** ficha la **transporte** sección, haga clic en el **configurar** situado junto a **tipo**.  

3. En el **propiedades de transporte de MSMQ** diálogo cuadro, realice lo siguiente:  


   |            Utilice esta propiedad            |                                                                                                                            Para                                                                                                                            |  Tipo de datos  | Valor predeterminado |
   |-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------|---------------|
   |              **Contraseña**               |                                                                                                 Especificar la contraseña de una cola remota. Usar con **nombre de usuario**.                                                                                                 |   String    |     En blanco     |
   |              **Nombre de usuario**              |                                                             Especificar el nombre de usuario de una cola remota. Usar con **contraseña**. No se puede utilizar el usuario local del equipo remoto como nombre de usuario.                                                             |   String    |     En blanco     |
   |        **Tipo de confirmación**         | Especificar el tipo de mensaje de confirmación que Message Queue Server debe devolver a la aplicación que realizó el envío. Puede seleccionar más de un tipo de confirmación. Cualquiera de los tipos de confirmación en el **System.Messaging.AcknowledgeTypes** enumeración están disponibles. |   String    |     None      |
   |        **Cola de administración**         |                                                                                                Especificar el nombre de la cola que recibe el mensaje de confirmación.                                                                                                 |   String    |     En blanco     |
   |              **Tipo de cuerpo**              |                                                                               Especificar el tipo de cuerpo del mensaje en MSMQ. Los valores válidos son miembros de .NET **VarEnum** enumeración.                                                                               |     int     |     8209      |
   |       **Huella digital del certificado**        |    Especificar la huella digital del certificado que se utilizará para la autenticación de mensajes. Utilice esta propiedad en combinación con la **usar autenticación** propiedad para comprobar el mensaje. Use la **nombre de usuario** y **contraseña** propiedades para obtener acceso a las colas.     |   String    |     En blanco     |
   |          **Cola de destino**          |                     Especificar la cola de destino. Para obtener más información acerca de las colas, consulte [colas de Message Queue Server](../core/message-queuing-queues.md). **Nota:** el URI para un envío de puerto o recibir ubicación no puede superar los 256 caracteres.                      |   String    |     En blanco     |
   |        **Algoritmo de cifrado**         |                                                                                                Seleccione **RC2**, **RC4**, o **ninguno** para el algoritmo de cifrado.                                                                                                |    Enum     |     None      |
   | **Tamaño máximo de mensaje (en kilobytes)** |                                                                                       Especificar el tamaño máximo del mensaje de los mensajes que se envían a la cola especificada.                                                                                        | UnsignedInt |     1024      |
   |          **Prioridad del mensaje**           |                                                                                                                    Establecer la prioridad del mensaje.                                                                                                                     |    Enum     |    Normal     |
   |             **Recuperables**             |                                                                                                  Especificar si se garantizará que se podrá recuperar un mensaje.                                                                                                   |   Boolean   |     False     |
   |        **Admitir segmentación**         |                                                                                        Establezca este valor de propiedad booleano en **True** para segmentar mensajes mayores de 4 MB.                                                                                         |   Boolean   |     False     |
   |               **Timeout**               |                                                                    Especificar el tiempo de espera máximo de los mensajes hasta alcanzar la cola de destino. Se aplica sólo cuando se utilizan transacciones.                                                                     |     int     |       0       |
   |            **Unidad de tiempo de espera**             |                                                                      Establecer la unidad que se usará para la **tiempo de espera** propiedad.<br /><br /> Seleccione **días**, **horas**, **minutos**, o **segundos**.                                                                      |    Enum     |     Días      |
   |            **Transaccional**            |                                                                                               Establezca este valor en **True** para enviar mensajes si se utilizan transacciones.                                                                                               |   Boolean   |     False     |
   |         **Usar la autenticación**          |     Establezca este valor de propiedad booleano en **True** para controlar la autenticación. Utilice esta propiedad en combinación con la **huella digital del certificado** propiedad para comprobar el mensaje. Use la **nombre de usuario** y **contraseña** propiedades para obtener acceso a las colas.      |   Boolean   |     False     |
   |        **Usar cola de mensajes**        |                                                                                    Establezca este valor en **True** para enviar mensajes a la cola si se produce un error.                                                                                     |   Boolean   |     True      |
   |          **Usar cola de diario**          |                                                                                   Establezca este valor en **True** para guardar una copia del mensaje cada vez que se procesa el mensaje.                                                                                    |   Boolean   |     False     |


4. Haga clic en **Aceptar** y **Aceptar** nuevo para guardar la configuración.  

## <a name="see-also"></a>Vea también  
 [Cómo configurar ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md)   
 [Configuración del adaptador de MSMQ](../core/configuring-the-msmq-adapter.md)