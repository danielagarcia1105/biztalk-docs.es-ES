---
title: Canalización de envío de crear el FRR | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, creating send pipelines
- creating, send pipelines
- send pipelines, creating
ms.assetid: c6cd2047-ea53-425f-80cc-b02a1deb5292
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87733b6b3a93d2543d26cd6d11b366b84218d207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209460"
---
# <a name="creating-the-frr-send-pipeline"></a>Crear la canalización de envío FRR
Para realizar la conciliación de respuesta de FIN, debe crear una canalización de envío que contiene el componente de canalización SWIFTAsmFrrMQSeriesHelper, además el ensamblador SWIFT.  
  
 **Resumen**  
  
 Crear una canalización de envío con las siguientes fases:  
  
|Fase|Componente|  
|-----------|---------------|  
|Fase de ensamblado|Ensamblador SWIFT|  
|Fase de codificación|Componente de MQSeries envío Frr SWIFT|  
  
### <a name="to-create-a-custom-send-pipeline-for-frr"></a>Para crear una canalización de envío personalizada para FRR  
  
1.  En el Explorador de soluciones de Visual Studio, haga clic en el proyecto de canalización, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el cuadro de diálogo Agregar nuevo elemento, seleccione **canalización de envío** desde el panel de plantillas.  
  
3.  En el **nombre** , escriba un nombre para la canalización de recepción, como **FRRSendPipeline.btp**. Haga clic en **Agregar**.  
  
4.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.  
  
5.  En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT ensamblador** a la **Coloque aquí los** cuadro siguiente la **ensamblar** almacenar provisionalmente la forma en **canalizaciones de BizTalk Diseñador**.  
  
6.  En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **SWIFT Frr MQSeries enviar componente** a la **Coloque aquí los** cuadro siguiente la **Encode** almacenar provisionalmente la forma en  **Diseñador de canalizaciones de BizTalk**.  
  
7.  En el Explorador de BizTalk, haga clic en el proyecto de canalización, haga clic en **anular la implementación**y, a continuación, haga clic en **Sí**.  
  
    > [!NOTE]
    >  Después de anular la implementación y, a continuación, volver a implementar el proyecto de canalización, debe restablecer los puertos de envío o ubicaciones de recepción que utilice canalizaciones en el proyecto implementado previamente.  
  
8.  En el Explorador de soluciones, haga clic en el proyecto de canalización y, a continuación, haga clic en **generar**.  
  
9. Después de la compilación finalice correctamente, haga clic en el proyecto de canalización y, a continuación, haga clic en **implementar**.