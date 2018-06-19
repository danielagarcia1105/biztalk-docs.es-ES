---
title: Ejemplo de HubScenario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb6990ec-aea2-4362-8573-7f737a4fc7f1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47f7ba8320a43cbfdc98a3b3e5becdce9a898f9
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006349"
---
# <a name="hubscenario-sample"></a>Ejemplo de HubScenario
El ejemplo de HubScenario muestra cómo administrar la transmisión de mensajes en un escenario de concentrador. Transforma un mensaje enviado a un concentrador intermediario en un mensaje que se enviará al destinatario final.  
  
 HubScenario extrae el número DUNS del destinatario final del contenido del servicio. Administra los certificados de firma y cifrado y la dirección URL de destino. Genera un nuevo mensaje para el destinatario final.  
  
 Este ejemplo gestiona mensajes de solicitud y respuesta 3A4, y mensajes de solicitud 0C1. Al usar HubScenario para crear una aplicación para sus propósitos, tendrá que generar rutinas para cada proceso de interfaz de socio (PIP) del mensaje.  
  
 El ejemplo de HubScenario incluye proyectos HubHelper.cs y HubScenario.odx.  
  
 El ejemplo de HubScenario también incluye un archivo de enlace que puede usar para importar enlaces para un puerto de recepción (MessagesToLOB_Receive_Port) y una ubicación de recepción (MessagesToLOB_Receive_Location) para su uso con la orquestación HubScenario.odx. Este archivo de enlace (HubScenarioBinding.xml) se encuentra en  *\<unidad\>*: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk \<versión\> Acelerador para RosettaNet \SDK\HubScenario. Use el comando BTSTask para importar los enlaces. Para obtener más información, vea el tema "Comando ImportBindings" en la Ayuda de BizTalk Server.  
  
### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En Visual Studio, abra \<unidad\>: \Program Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\HubScenario\HubScenario.btproj. En el Explorador de soluciones, haga clic con el botón derecho en el proyecto HubScenario y, a continuación, haga clic en Propiedades. En la página Propiedades del proyecto HubScenario, en la ficha Firma, seleccione la casilla de verificación **Firmar el ensamblado** y seleccione **HubScenario.snk** en **Elija un archivo de clave de nombre seguro** y haga clic en **Aceptar**.  
  
2.  En el Explorador de soluciones, haga clic con el botón derecho en el proyecto HubHelper y, a continuación, haga clic en Propiedades. En la página Propiedades del proyecto HubHelper, en la ficha Firma, marque la casilla de verificación Firmar el ensamblado. En Elija un archivo de clave de nombre seguro, seleccione el nuevo tipo **HubHelper.snk** como nombre de archivo de clave y haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si no especifica manualmente el archivo de clave de ensamblado en los proyectos HubScenario y HubHelper, los ensamblados no se implementarán.  
  
3.  En un símbolo del sistema, vaya a  *\<unidad\>*: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\ Carpeta de HubScenario. Ejecute el archivo Setup.bat (o Setupx64.bat en un equipo de 64 bits).  
  
## <a name="demonstrates"></a>Demostraciones  
 La orquestación HubScenario.ods muestra cómo realizar las tareas siguientes:  
  
1.  Recibe el mensaje de la aplicación de línea de negocio.  
  
2.  Quita el elemento `CDATA` del contenido del servicio y devuelve la cadena XML.  
  
3.  Recupera el nombre de la entidad de destino, PIPCode, PIPInstanceID y PIPVersion para el mensaje final.  
  
4.  Recupera el número DUNS para el destinatario final.  
  
5.  Determina la categoría del mensaje y agrega el elemento DOCTYPE que contiene una referencia al esquema adecuado para el contenido del servicio.  
  
6.  Construye un mensaje con el nuevo nombre de entidad de destino, número DUNS, información de código PIP y contenido del servicio.  
  
7.  Envía el mensaje para su procesamiento mediante [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]. Se trata de una llamada a `SubmitRNIF.SubmitMessage`.  
  
## <a name="see-also"></a>Vea también  
 [Escenario de ejemplo basado en concentrador](../../adapters-and-accelerators/accelerator-rosettanet/sample-hub-based-scenario.md)   
 [Ejemplos de orquestación](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)