---
title: 'Tutorial 2: EDI Interface Developer Tutorial | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10fb650-cbb9-41e5-a80d-06afd0513814
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f995cc21bd94ddc00ab15d78c74679eb51d939b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020433"
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a>Tutorial 2: Tutorial de desarrollador de la interfaz EDI
Este tutorial muestra cómo usar la funcionalidad EDI en un escenario de desarrolladores de interfaz de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 **Escenario del tutorial**  
  
 En este escenario, su socio comercial envía pedidos de compra a su compañía mediante el conjunto de transacciones 850 de ANSI X12 versión 4010 (un mensaje 850). Su compañía utiliza una aplicación interna, el sistema de pedidos, para procesar los pedidos de compra.  
  
 Usted es el programador responsable del diseño de la interfaz entre el mensaje 850 que recibe de su socio comercial y el sistema de pedidos interno de la compañía. Su socio comercial requiere una confirmación funcional (997) para cada mensaje 850 que envía.  
  
 Para facilitar la referencia, se utilizan los siguientes identificadores:  
  
|Entidad|Identificador|  
|------------|----------------|  
|Su compañía|El sistema de pedidos|  
|Su socio comercial|Fabrikam|  
  
 El flujo de mensajes en la solución completa será como se muestra a continuación:  
  
 ![Flujo de mensajes EDI Interface Developer Tutorial](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")  
  
 **Flujo de mensajes**  
  
 La solución de este tutorial hará lo siguiente:  
  
1. Recibir un intercambio de archivos sin formato del socio comercial Fabrikam.  
  
   > [!NOTE]
   >  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  
  
2. Validar el intercambio EDI con su esquema, desensamblar el mensaje a XML y depositar el mensaje XML en el cuadro de mensajes.  
  
3. Generar una confirmación 997 al intercambio EDI recibido y depositarla en el cuadro de mensajes.  
  
4. Recoger el XML de 997 mediante un puerto de envío unidireccional y ensamblar el intercambio EDI 997.  
  
5. Enviar un intercambio 997 a Fabrikam.  
  
6. Recoger el XML del mensaje mediante un puerto de envío unidireccional y ensamblar el intercambio EDI del mensaje.  
  
7. Enviar un intercambio EDI a OrderSystem.  
  
   **Configuración**  
  
   En este tutorial, llevará a cabo lo siguiente:  
  
- Configurar BizTalk para recibir un mensaje 850 de su socio comercial y devolver una confirmación 997.t  
  
- Utilizar una asignación de BizTalk para convertir el mensaje 850 al formato necesario según el sistema de pedidos. Este mapa se proporciona en los archivos del tutorial en el SDK de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
- Configurar un puerto de recepción para recibir el mensaje 850.  
  
- Configurar un puerto de envío para enviar el mensaje 850 a OrderSystem en el formato correcto.  
  
- Configurar un puerto de envío para que se suscriba a la confirmación 997 generada por BizTalk y la devuelva al socio comercial, Fabrikam.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Prepara el tutorial de programadores de interfaces de EDI](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [Paso 2: Actualizar e implementar la solución del tutorial](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [Paso 3: Configurar un perfil de entidad y negocio para la organización](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [Paso 4: Configurar un perfil de entidad y negocio para el socio comercial](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [Paso 5: Configurar un puerto y una ubicación de recepción](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [Paso 6: Configurar un puerto de envío para enviar datos a la organización](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [Paso 7: Configurar un puerto de envío para enviar la confirmación al socio comercial](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [Paso 8: Configurar el acuerdo entre socios comerciales entre las entidades](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [Paso 9: Probar la solución EDI](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutoriales de BizTalk Server](../core/biztalk-server-tutorials.md)