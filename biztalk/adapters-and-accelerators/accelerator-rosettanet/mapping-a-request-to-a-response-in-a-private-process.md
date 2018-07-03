---
title: Asignar una solicitud a una respuesta en un proceso privado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- private processes, mapping requests
- private processes, customizing
- orchestrations, adding maps
- maps, adding to orchestrations
- maps, creating
- customizing private processes
- requests, mapping
- requests, private processes
ms.assetid: 5452c0a2-3a9b-43e7-bfa7-713eef0eab3b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb7cab4ba412a46f61df89daefd86df260454195
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976229"
---
# <a name="mapping-a-request-to-a-response-in-a-private-process"></a>Asignar una solicitud a una respuesta en un proceso privado
En este tema se describe cómo asignar un mensaje de solicitud recibido por el proceso del Respondedor privado, de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proceso público del servicio de respuesta, en un mensaje de respuesta que se puede enviar a la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] proceso público del Respondedor.  
  
 Cuando un servicio de respuesta recibe un mensaje de solicitud, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enruta el mensaje de solicitud de la orquestación de proceso público a la orquestación de procesos privado, el programa de línea de negocio (LOB). El servicio de respuesta requiere el contenido del servicio de respuesta desde el programa de línea de negocio para generar un mensaje de RosettaNet respuesta al iniciador. Muchos de los elementos en el mensaje de respuesta se rellenan con los valores del mensaje de solicitud. Como resultado, puede incorporar un mapa en la orquestación de proceso privado del Respondedor para ayudar a que el sistema LOB generar el mensaje de contenido del servicio de respuesta en el formato requerido.  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK contiene los siguientes ejemplos que puede usar al agregar un mapa a un proceso privado del Respondedor:  
  
-   [Solicitud de 3A2 al ejemplo de asignación de respuesta de 3A2](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)  
  
-   [Solicitud de 3A4 al ejemplo de asignación de respuesta de 3A4](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)  
  
-   [Orquestación PIPAutomation de acción doble](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)  
  
-   [Orquestación del respondedor privado 3A4 mediante una regla de negocio](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)  
  
### <a name="to-create-the-map"></a>Para crear la asignación  
  
1.  Inicie **Microsoft Visual Studio 2012**.  
  
2.  En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.  
  
3.  Busque la carpeta que contiene el proyecto de BizTalk que contiene la orquestación de proceso de privado a la que desea agregar el mapa.  
  
4.  En el Explorador de soluciones, haga clic con el botón derecho en el proyecto, seleccione **Agregar** y, después, haga clic en **Nuevo elemento**.  
  
5.  En la ventana Agregar nuevo elemento, en el **categorías** panel, haga clic en **archivos de asignación**. En el panel Plantillas, haga clic en **mapa**. En el **nombre** , escriba un nombre para el mapa y, a continuación, haga clic en **abierto**.  
  
6.  En el panel Esquema de origen, haga clic en **Abrir esquema de origen**.  
  
7.  En la ventana del selector de tipos de BizTalk, expanda **esquemas**, seleccione el esquema PIP para el mensaje de solicitud que desea crear una asignación de y, a continuación, haga clic en **Aceptar**.  
  
8.  En el panel Esquema de destino, haga clic en **Abrir esquema de destino**.  
  
9. En la ventana del selector de tipos de BizTalk, expanda **referencias**, expanda **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expanda **esquemas**, seleccione el esquema PIP para el mensaje de respuesta a la que desea asignar y, a continuación, haga clic en **Aceptar**.  
  
10. Haga clic en el \< *esquema* \> nodo del esquema de origen y, a continuación, haga clic en **Expandir nodo de árbol**.  
  
11. Repita el paso 10 para el esquema de destino.  
  
12. En el panel Esquema de origen, haga clic y mantenga en un campo que desea asignar a un campo del esquema de destino. Arrastre hasta el nodo correspondiente en el panel de esquema de destino.  
  
13. Repita el paso 12 para todos los campos que se deben asignar entre los dos esquemas.  
  
14. Valide y pruebe la asignación. Para obtener más información, vea el tema "Compilar y probar asignaciones" en la Ayuda de BizTalk Server.  
  
### <a name="to-add-the-map-to-the-orchestration"></a>Para agregar la asignación a la orquestación  
  
1.  En el Explorador de soluciones, haga doble clic en la orquestación de procesos de privados.  
  
    > [!NOTE]
    >  Asegúrese de que la orquestación tiene referencias a los ensamblados que contienen los esquemas.  
  
2.  En el cuadro de herramientas, haga clic en el **transformar** dar forma y arrástrelo hasta el punto en la orquestación a la que tiene que transformar el mensaje de solicitud en el mensaje de respuesta.  
  
    > [!NOTE]
    >  Para obtener un ejemplo de la colocación de la **transformar** forma, vea la orquestación PIP3A4PrivateResponder.odx. Se encuentra en \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\PipAutomation\3A4\PR. Este ejemplo coloca el **transformar** forma inmediatamente bajo la **IsActivityDoubleAction** forma. Para obtener más información, consulte [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).  
  
    > [!NOTE]
    >  Para obtener un ejemplo de cómo puede incorporar varios mapas para varios PIP, consulte [orquestación PIPAutomation de acción doble](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).  
  
3.  En la superficie de diseño de orquestación, haga clic en **ConstructMessage1**. En la ventana Propiedades, escriba un nombre para la forma y un nombre para el mensaje que se va a construir.  
  
4.  En la superficie de diseño de orquestación, haga clic en **transformar**. En la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) junto a **nombre de asignación**.  
  
5.  En la ventana de configuración de transformación, haga clic en **mapa existente**y en **nombre completo de asignación**, haga clic en el mapa que acaba de crear.  
  
6.  En **transformar**, haga clic en **origen**. Haga clic en el cuadro vacío en la variable y seleccione el nombre del mensaje de solicitud en la lista desplegable.  
  
7.  En **transformar**, haga clic en **destino**. Haga clic en el cuadro vacío en la variable y seleccione el nombre del mensaje de respuesta de la lista desplegable.  
  
8.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)