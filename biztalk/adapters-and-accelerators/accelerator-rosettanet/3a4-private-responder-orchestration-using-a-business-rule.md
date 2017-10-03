---
title: "Orquestación de Respondedor privada de 3A4 mediante una regla de negocios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33d87952-def6-4202-b535-3d80171332eb
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 716ce7b5ac97ef424c815080a61877725db63443
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="3a4-private-responder-orchestration-using-a-business-rule"></a>Orquestación de Respondedor privada de 3A4 mediante una regla de negocios
El ejemplo PIP3A4PrivateResponder.odx es una orquestación de procesos privados que muestra cómo implementar un proceso de interfaz de socio (PIP)-procesos privados Respondedor específico que incorpore una regla de negocios. Para obtener más información acerca de este proceso, consulte [definir una regla de negocios para una orquestación de procesos privado](../../adapters-and-accelerators/accelerator-rosettanet/defining-a-business-rule-for-a-private-process-orchestration.md).  
  
 De forma predeterminada, el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] programa de instalación instala el ejemplo en \< *unidad*>: \Program BizTalk \<versión > Accelerator for RosettaNet\SDK\PipAutomation \3A4.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En un símbolo del sistema, busque la  *\<unidad >*: \Program Files\ Acelerador de Microsoft BizTalk para RosettaNet \<versión > carpeta \SDK\PIPAutomation\3A4.  
  
2.  Ejecute el archivo Setup.bat, que utiliza el archivo de enlace de Binding.xml para realizar las siguientes acciones:  
  
    -   Compila el proyecto de aplicación auxiliar y registra el ensamblado en la caché global de ensamblados.  
  
    -   Compila el proyecto PIP3APrivateResponder y registra el ensamblado en la caché global de ensamblados.  
  
    -   Crea el LOB_To_PrivateResponder puerto de recepción.  
  
    -   Crea la LOB_To_PrivateResponder ubicación de recepción.  
  
    -   Crea e inicia el puerto de envío PrivateResponder_To_LOB.  
  
    -   Compila e implementa la orquestación PIP3A4PrivateResponderProcess.  
  
    > [!NOTE]
    >  Debe completar la configuración de enlace de puerto de la orquestación de PIP3A4PrivateResponderProcess mediante el Explorador de BizTalk.  
  
    > [!NOTE]
    >  Para deshacer los cambios realizados por setup.bat, dar de baja la orquestación de PIP3A4PrivateResponder.odx manualmente, anular la implementación de los ensamblados de aplicación auxiliar y PIP3A4PrivateResponder y anular la implementación y, a continuación, elimine la directiva de reglas de samplebtarnpolicy. No se puede utilizar Cleanup.bat en la  *\<unidad >*: \Program Files\ Acelerador de Microsoft BizTalk para RosettaNet \<versión > carpeta \SDK\PIPAutomation\3A4 para deshacer los cambios realizados por setup.bat.  
  
## <a name="demonstrates"></a>Demostraciones  
 En este ejemplo se suscribe a mensajes de acción y señal de solicitud de 3A4. Funciona en ambos procesos de 3A4 sincrónicas y asincrónicas. Todos los demás mensajes PIP sigue enrutan a través de la interfaz genérica [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesos privados. En este ejemplo, se invoca el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] motor de reglas de negocios y pasa a la regla de mensaje de solicitud entrante 3A4 del motor.  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Proporciona una directiva de reglas de negocio de ejemplo denominada samplebtarnpolicy.XML, en \< *unidad*>: \Program Files\ Acelerador de Microsoft BizTalk para RosettaNet \<versión > \SDK\PipAutomation\3A4. Para obtener más información, consulte [directiva empresarial de BTARN de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).  
  
 Para trabajar con el ejemplo, configurar una regla de negocios. Si el mensaje cumple la regla de negocios, el proceso guarda el mensaje entrante de acción en la tabla MessagesToLOB, si el estado de entrega se establece en 2. El valor de columna entregado debe ser distinto de cero, para que la aplicación de línea de negocio sepa que no es necesario que generar una confirmación para esta solicitud. El proceso, a continuación, el mensaje de solicitud de 3A4 se asigna a un mensaje de confirmación de 3A4 y envía la respuesta a la tabla MessageStorageIn mediante la `SubmitRNIF` método.  
  
 Si el mensaje no cumple la regla de negocios, el proceso guarda el mensaje entrante de acción en la tabla MessageStorageOut y estado de entrega establece en 0.  
  
 Este ejemplo incluye un archivo de enlace (Binding.xml) que puede usar para configurar un puerto de envío (PrivateResponder_To_LOB), un puerto de recepción (LOB_To_PrivateResponder) y una ubicación de recepción (LOB_To_PrivateResponder) para su uso con el PIP3A4PrivateResponder.odx orquestación. Utilice el comando BTSTask para importar los enlaces en el archivo Binding.xml. Para obtener más información, vea el tema "Comando ImportBindings" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
## <a name="see-also"></a>Vea también  
 [Orquestación PIPAutomation de acción doble](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)   
 [Directiva empresarial BTARN de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)   
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)