---
title: To-End SimulationTutorial1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.endtoendtutorial
helpviewer_keywords:
- end-to-end tutorial, about the tutorial
- end-to-end tutorial
- tutorials, end-to-end tutorial
ms.assetid: 90625edc-70a0-42c9-a2fb-8eeb5465d766
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 264a6eee008b9b327185c931ad4e5ac60cdc995a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000741"
---
# <a name="end-to-end-tutorial"></a>Tutorial de extremo a otro
Este tutorial contiene los pasos detallados que describen cómo utilizar Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para facilitar procesos empresariales en un escenario de suscriptor y el publicador.  
  
> [!IMPORTANT]
>  Para usar este tutorial, debe instalar las herramientas de prueba al instalar BTAHL7. Si ha realizado una instalación típica para instalar BTAHL7, debe ejecutar una instalación personalizada e instalar las herramientas de prueba para este tutorial funcione correctamente. En el **instalación personalizada** pantalla de la instalación personalizada de BTAHL7, seleccione **herramienta de prueba de MLLP** desde el **adaptador** carpeta y seleccione **delasinstanciasdeprueba** desde el **artefactos** carpeta. Para obtener más información, consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).  
  
## <a name="declarative-scenario"></a>Escenario de declaración  
 Este tutorial usa el escenario declarativa o publicación/suscripción. En el escenario declarativo, el flujo de negocio es similar al que se muestra en la ilustración siguiente. La lista numerada de la figura siguiente describe el flujo de trabajo.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")  
Ilustración que muestra el flujo de negocio para el escenario declarativo  
  
1.  El flujo de trabajo comienza cuando el publicador, por ejemplo, una estancia de pacientes y del sistema de transferencia, envía un mensaje a suscriptores específicos. El publicador en el flujo de trabajo es "Tutorial_ADTSystem" y el mensaje se denomina "**ADT ^ A103**."  
  
2.  El mensaje se enruta al motor de interfaz de BTAHL7, que a su vez recibe, procesa, valida, vuelve a dar formato y, a continuación, enruta el mensaje a los suscriptores.  
  
3.  Los suscriptores en este escenario son un sistema de información de Hospital (Tutorial_HISystem) y un sistema de farmacia (Tutorial_RXSystem). Este escenario utiliza tipos de adaptador de archivo y de MLLP. El publicador no necesita ser consciente de los suscriptores y BTAHL7 adecuadamente envía una confirmación al publicador después de procesar el mensaje.  
  
4.  El publicador envía el ADT ^ A03 mensaje a través de un adaptador de MLLP unidireccional (Tutorial_1WayReceivePort).  
  
5.  El destino de este mensaje es el motor de la interfaz de BTAHL7, por lo que el mensaje entrante contiene un mensaje de origen (MSH3 = Tutorial_ADTSystem) y un mensaje de destino (MSH5 = BTAHL7InterfaceEngine).  
  
6.  BTAHL7 genera una confirmación (ACK) después de validar correctamente el mensaje y, a continuación, envía la confirmación a la Tutorial_ADTSystem a través del adaptador de archivo.  
  
7.  El sistema Tutorial_HISystem y el sistema Tutorial_RXSystem suscriben al mensaje ADT recibido por el motor de la interfaz de BTAHL7.  
  
8.  La transformación se produce al especificar valores para los campos correspondientes usando el **asignación de MSH** ficha en el Explorador de configuración de BTAHL7.  
  
     Por ejemplo, la entidad Tutorial_RXSystem tiene MSH3 = BTHL7 especificado en el **asignación de MSH** ficha. Por lo tanto, el mensaje recibido por el suscriptor tendrá "BTAHL7" como el valor del campo MSH3.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Probar la instalación](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [Preparación para usar el tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [Paso 1: Crear e implementar esquemas de encabezado y confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [Paso 2: Creación de esquemas comunes para v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [Paso 4: Crear el puerto de recepción para aceptar mensajes ADT^A03 desde sistemas ADT mediante el adaptador de MLLP](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [Paso 5: Crear un puerto de envío para entregar confirmaciones al sistema ADT mediante el adaptador de archivo](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [Paso 6: Crear un puerto de envío para entregar el mensaje ADT^A03 al sistema RX mediante el adaptador de archivo](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [Paso 7: Crear un puerto de envío para entregar el mensaje ADT^A03 a HIS mediante el adaptador de MLLP](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [Paso 8: Configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [Paso 9: Reiniciar BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [Paso 10: Comprobar el escenario integral](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a>Vea también
[Introducción al Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)