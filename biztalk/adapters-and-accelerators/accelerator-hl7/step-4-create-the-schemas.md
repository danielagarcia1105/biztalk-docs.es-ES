---
title: 'Paso 4: Crear los esquemas | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, schemas
- creating, schemas
- schemas, creating
ms.assetid: 81b1f538-9743-433a-87f9-a423dcb868c8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ce9ea850632327e257909e1c7d4b60117865e46
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="step-4-create-the-schemas"></a>Paso 4: Crear los esquemas
En este paso, creará un nuevo proyecto (**BTAHL7 proyecto**) que contiene los artefactos para este proyecto: los esquemas, el mapa y la orquestación. A continuación, cree un esquema (**Doorbell.xsd**) para el mensaje entrante de codificación XML y seleccione un esquema existente (**ADT_A04_22_GLO_DEF.xsd**) para el mensaje saliente con codificación HL7. Use estos esquemas para definir la estructura de los mensajes que intercambian en la orquestación.  
  
### <a name="to-create-the-schemas"></a>Para crear los esquemas  
  
1.  En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.  
  
2.  En el cuadro de diálogo nuevo proyecto, expanda el **proyectos de BizTalk** carpeta y, a continuación, haga clic en el **BTAHL7Projects** carpeta.  
  
3.  En el **plantillas** panel, haga clic en **proyecto vacío de BTAHL7**.  
  
4.  En el **nombre** , escriba **BTAHL7 proyecto** como el nombre del proyecto.  
  
5.  En el **solución** campo, seleccione **agregar a solución**.  
  
6.  En el **ubicación** , a continuación, compruebe que  **\< *unidad*\>: \Tutorial\BTAHL7V22Common** es la ruta de acceso.  
  
7.  Haga clic en **Aceptar** para abrir el nuevo proyecto.  
  
    > [!NOTE]
    >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]Agrega un nuevo proyecto en el Explorador de soluciones. También agrega la carpeta del proyecto y crea archivos de la \< *unidad*\>: \Tutorial\\**BTAHL7V22Common** carpeta del proyecto.  
  
8.  En el Explorador de soluciones, haga clic en el **BTAHL7 proyecto** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
9. En Agregar nuevo elemento - proyecto BTAHL7 cuadro de diálogo, en la **categorías** panel, haga clic en **archivos de esquema**y en el **plantillas** panel, haga clic en **esquema**.  
  
10. En el **nombre** , escriba **Doorbell.xsd** al nombre del esquema.  
  
11. Haga clic en **agregar** para abrir el esquema en blanco en el Editor de BizTalk.  
  
12. En el  **\<esquema\>**  de árbol, haga clic en el **raíz** nodo y, a continuación, haga clic en **cambiar el nombre de**.  
  
13. Tipo de **DoorbellRoot** como nuevo nombre y, a continuación, presione **ENTRAR**.  
  
14. Haga clic en el **DoorbellRoot** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario** para agregar los campos siguientes (Repita este paso para cada campo elemento):  
  
    -   **FirstName**  
  
    -   **MiddleName**  
  
    -   **LastName**  
  
    -   **SSN**  
  
15. En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
16. En Agregar nuevo elemento - proyecto BTAHL7 cuadro de diálogo, en la **categorías** panel, haga clic en **BTAHL7 esquemas**y, a continuación, haga clic en **agregar**.  
  
17. En el cuadro de diálogo Selector de esquema HL7, en la **Message (clase)** cuadro, seleccione **V2.X**y en el **detalles del esquema** panel, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Versión**|Seleccione el número de versión del mensaje HL7. En este tutorial, usará **2.2**.|  
    |**Tipo de mensaje**|Seleccione el tipo de mensaje HL7. En este tutorial, usará **ADT**.|  
    |**Evento de desencadenador**|Seleccione el valor de evento de desencadenador para el mensaje HL7. En este tutorial, usará **A04**.|  
  
18. Haga clic en **finalizar** para agregar el esquema ADT_A04_22_GLO_DEF.xsd (registrar paciente) a su proyecto. Cierre el cuadro de diálogo Selector de esquema HL7.  
  
19. En el Explorador de soluciones, bajo **BTAHL7 proyecto**, haga clic en **referencias** y, a continuación, haga clic en **Agregar referencia**.  
  
20. En el cuadro de diálogo Agregar referencia, en la **proyectos** ficha, seleccione la **BTAHL7V22Common** proyecto de equipo y haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Esto agrega una referencia al proyecto original para que [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] reconoce los esquemas de HL7 correctamente.  
  
21. En el Explorador de soluciones, bajo **BTAHL7 proyecto**, haga clic en **referencias** y, a continuación, haga clic en **Agregar referencia**.  
  
22. En el cuadro de diálogo Agregar referencia, haga clic en el **examinar** ficha. En el **buscar en** cuadro, pase a \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para Tutorial HL7\SDK\End-to-End \Tutorial_BTAHL7Drop\Bin. Haga clic en **Microsoft.Solutions.BTAHL7.HL7Schemas.dll**, haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.  
  
 Continúe con [paso 5: promocionar las propiedades de esquema](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)