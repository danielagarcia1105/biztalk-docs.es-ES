---
title: Orquestación del Respondedor privado 3A4 mediante una regla de negocios | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33d87952-def6-4202-b535-3d80171332eb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9ca606aa3d8ce6cdb74d4653e910f7db7639ec3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986101"
---
# <a name="3a4-private-responder-orchestration-using-a-business-rule"></a>Orquestación del Respondedor privado 3A4 mediante una regla de negocios
El ejemplo PIP3A4PrivateResponder.odx es una orquestación de procesos privados que muestra cómo implementar un proceso de interfaz de socio (PIP)-incorporación de una regla de negocios de procesos privado Respondedor específico. Para obtener más información sobre este proceso, consulte [definir una regla de negocios para una orquestación de procesos privado](../../adapters-and-accelerators/accelerator-rosettanet/defining-a-business-rule-for-a-private-process-orchestration.md).  
  
 De forma predeterminada, el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] programa de instalación instala en el ejemplo de \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet \SDK\PipAutomation\3A4.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1.  En un símbolo del sistema, busque el  *\<unidad\>*: Acelerador de Microsoft BizTalk para RosettaNet \Program Files\ \<versión\>\SDK\PIPAutomation\3A4 carpeta.  
  
2.  Ejecute el archivo Setup.bat, que usa el archivo de enlace de Binding.xml para realizar las siguientes acciones:  
  
    -   Compila el proyecto de aplicación auxiliar y registra el ensamblado en la caché global de ensamblados.  
  
    -   Compila el proyecto PIP3APrivateResponder y registra el ensamblado en la caché global de ensamblados.  
  
    -   Crea el LOB_To_PrivateResponder puerto de recepción.  
  
    -   Crea el LOB_To_PrivateResponder ubicación de recepción.  
  
    -   Crea e inicia el puerto de envío PrivateResponder_To_LOB.  
  
    -   Compila e implementa la orquestación PIP3A4PrivateResponderProcess.  
  
    > [!NOTE]
    >  Debe completar la configuración de enlace de puerto de la orquestación PIP3A4PrivateResponderProcess mediante el Explorador de BizTalk.  
  
    > [!NOTE]
    >  Para deshacer los cambios realizados por setup.bat, manualmente dar de baja la orquestación PIP3A4PrivateResponder.odx, anular la implementación de los ensamblados de aplicación auxiliar y PIP3A4PrivateResponder y anular la implementación y, a continuación, eliminar la directiva de reglas samplebtarnpolicy. No se puede usar Cleanup.bat en el  *\<unidad\>*: Acelerador de Microsoft BizTalk para RosettaNet \Program Files\ \<versión\>\SDK\PIPAutomation\3A4 carpeta para deshacer los cambios realizados por setup.bat.  
  
## <a name="demonstrates"></a>Demostraciones  
 En este ejemplo se suscribe a mensajes de acción y señal solicitud 3A4. Funciona en ambos procesos de 3A4 sincrónicas y asincrónicas. Todos los demás mensajes PIP seguir enrutando a través del genérico [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proceso privado. En este ejemplo se invoca el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] motor de reglas de negocio y pasa a la regla de mensaje de solicitud entrante 3A4 del motor.  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Proporciona una directiva de reglas de negocio de ejemplo denominada samplebtarnpolicy.XML, en \< *unidad*\>: Acelerador de Microsoft BizTalk para RosettaNet \Program Files\ \<versión\>\SDK\ PipAutomation\3A4. Para obtener más información, consulte [directiva empresarial de BTARN de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).  
  
 Para trabajar con el ejemplo, configure una regla de negocios. Si el mensaje cumple la regla de negocios, el proceso guarda el mensaje entrante de acción en la tabla MessagesToLOB, estableciendo el estado de entrega en 2. El valor de columna entregado debe ser distinto de cero, para que sepa que la aplicación de línea de negocio que no es necesario que generar una confirmación para esta solicitud. El proceso, a continuación, el mensaje de solicitud de 3A4 se asigna a un mensaje de confirmación de 3A4 y envía la respuesta a la tabla MessageStorageIn mediante el `SubmitRNIF` método.  
  
 Si el mensaje no cumple la regla de negocios, el proceso guarda el mensaje entrante de acción en la tabla MessageStorageOut y estado de entrega establece en 0.  
  
 Este ejemplo incluye un archivo de enlace (Binding.xml) que puede usar para configurar un puerto de envío (PrivateResponder_To_LOB), un puerto de recepción (LOB_To_PrivateResponder) y una ubicación de recepción (LOB_To_PrivateResponder) para su uso con el PIP3A4PrivateResponder.odx orquestación. Use el comando BTSTask para importar los enlaces en el archivo Binding.xml. Para obtener más información, vea el tema "Comando ImportBindings" en la Ayuda de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Orquestación PIPAutomation de acción doble](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)   
 [Directiva empresarial BTARN de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)   
 [Ejemplos de orquestación](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)