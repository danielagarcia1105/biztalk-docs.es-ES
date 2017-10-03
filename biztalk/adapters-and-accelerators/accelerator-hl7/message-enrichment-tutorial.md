---
title: Tutorial de enriquecimiento de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial
- message enrichment tutorial, about the tutorial
- messages, tutorial
- tutorials, message enrichment tutorial
ms.assetid: 4ffb047f-457a-4a80-b7ec-4b61ae16f35f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 532fc0e8a9aeefbc35a892277c68be8d640b5588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-enrichment-tutorial"></a>Tutorial de enriquecimiento de mensajes
Este tutorial proporciona procedimientos paso a paso para usar [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para resolver un problema empresarial determinado: el problema de enriquecimiento del mensaje. El tutorial de enriquecimiento de mensajes describe una situación en la que se deben agregar a, o enriquecer, un mensaje que no es compatible con HL7 o está incompleta. Esto puede ocurrir con una aplicación, como una aplicación de registro del paciente, o puede producirse cuando se rellena un mensaje con datos XML de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].  
  
 En este tutorial, capturar los mensajes con BTAHL7 y proporcionar los datos que faltan, por ejemplo, desde una base de datos de registros de pacientes. A continuación, convertir el mensaje y enviarlo a un laboratorio, seguro o cualquier aplicación heredado línea de negocio (LOB) usa el adaptador MLLP (protocolo mínimos de nivel inferior).  
  
 En este tutorial, utilice una aplicación de cliente (WSClient.exe) del servicio Web para enviar un mensaje con formato XML, en este caso, un evento de desencadenador "timbre" registrar paciente, a través del adaptador SOAP para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] con BTAHL7. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]recibe el mensaje SOAP en el puerto de recepción y las rutas que publica el mensaje a una orquestación como servicio Web. El mensaje XML contiene un nombre del paciente y el número del seguro social. Aumentar el mensaje y usar los esquemas, un mapa y una transformación para convertir el mensaje en formato de HL7. A continuación, se envía a través de un adaptador MLLP para el laboratorio, seguro, o de las aplicaciones LOB.  
  
 En la siguiente ilustración muestra el flujo de proceso del tutorial.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")  
  
> [!NOTE]
>  Este tutorial requiere Windows Server Standard, Enterprise, Datacenter o Web Edition y una instalación de BTAHL7 personalizada que incluye la MLLP herramientas de prueba. Además, debe estar familiarizado con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] desarrollo en [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] y la información que se encuentra en [obtener información sobre el Acelerador para HL7 y las herramientas de BizTalk disponibles](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).  
  
> [!NOTE]
>  Puede evitar errores al anular la implementación de ensamblados, detener puertos de envío, y deshabilitar ubicaciones de recepción que utilizan en los tutoriales anteriores.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Configurar la identidad del grupo de aplicaciones](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [Paso 2: Crear un nuevo proyecto](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [Paso 3: Asignar un nombre seguro al ensamblado](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [Paso 4: Crear los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [Paso 5: Promocionar las propiedades de esquema](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [Paso 6: Validar los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [Paso 7: Firmar y compilar los proyectos](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [Paso 8: Crear un mapa con el asignador de BizTalk](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [Paso 9: Validar y compilar el proyecto de mapa](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [Paso 10: Crear una orquestación](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [Paso 11: Crear Variables de orquestación](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [Paso 12: Configurar formas de orquestación](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [Paso 13: Crear y configurar puertos](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [Paso 14: Publicar la orquestación como servicio Web](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [Paso 15: Configurar el envío y puertos de recepción](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [Paso 16: Iniciar la orquestación](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [Paso 17: Crear la aplicación WSClient](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [Paso 18: Probar la nueva solución de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)