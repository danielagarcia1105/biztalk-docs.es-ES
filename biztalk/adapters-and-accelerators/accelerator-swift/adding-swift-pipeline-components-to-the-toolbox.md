---
title: "Agregar componentes de canalización SWIFT al cuadro de herramientas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbox, adding pipelines
- pipelines, adding to toolbox
ms.assetid: 3821c10e-ef9b-4657-b934-cff6d096f654
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aaef345994a1d849e09025d9ad1bb0f133c1b224
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-swift-pipeline-components-to-the-toolbox"></a>Agregar componentes de canalización SWIFT al cuadro de herramientas
Debe agregar los componentes de canalización SWIFT a la [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] cuadro de herramientas, para que pueda crear canalizaciones personalizadas mediante estos componentes. Esto es necesario para crear canalizaciones de reparación de mensajes y nuevo envío o conciliación de respuesta de FIN.  
  
 **Resumen**  
  
 Agregue los siguientes componentes de canalización SWIFT para el [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] cuadro de herramientas:  
  
-   Ensamblador SWIFT (para la reparación de mensajes y nuevo envío o la conciliación de respuesta FIN (FRR))  
  
-   Desensamblador SWIFT (para la reparación de mensajes y nuevo envío o FRR)  
  
-   Resolución de conjunto de correlación de SWIFT Frr (para FRR)  
  
-   Descodificador de MQSeries SWIFT Frr (para FRR)  
  
-   Componente de envío SWIFT Frr MQSeries (para FRR)  
  
### <a name="to-add-a4swift-pipeline-components-to-the-toolbox"></a>Para agregar componentes de canalización de A4SWIFT al cuadro de herramientas  
  
1.  En Visual Studio, en el **herramientas** menú, haga clic en **elegir elementos del cuadro de herramientas**.  
  
2.  En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, en la **componentes de canalización de BizTalk** ficha, seleccione **SWIFT ensamblador** y **SWIFT Desensamblador**. Si va a utilizar Conciliación de respuesta de FIN, seleccione **resolución de conjunto de correlación de SWIFT Frr**, **SWIFT Frr MQSeries descodificador**, y **SWIFT Frr MQSeries enviar componente**.  
  
3.  Haga clic en **Aceptar**.