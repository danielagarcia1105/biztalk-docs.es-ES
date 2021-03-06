---
title: Canalización de envío de la creación de la FRR | Microsoft Docs
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
ms.openlocfilehash: d16003e489944016a7b840b870d33d8ebcf671d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005749"
---
# <a name="creating-the-frr-send-pipeline"></a>Creación de la canalización de envío FRR
Para llevar a cabo la conciliación de respuestas de FIN, deberá crear una canalización de envío que contiene el componente de canalización SWIFTAsmFrrMQSeriesHelper, además del ensamblador de SWIFT.  

 **Resumen**  

 Crear una canalización de envío con las siguientes fases:  

|Fase|Componente|  
|-----------|---------------|  
|Fase de ensamblado|Ensamblador de SWIFT|  
|Fase de codificación|Componente de MQSeries envío Frr SWIFT|  

### <a name="to-create-a-custom-send-pipeline-for-frr"></a>Para crear una canalización de envío personalizado de FRR  

1. En el Explorador de soluciones de Visual Studio, haga clic en el proyecto de canalización, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  

2. En el cuadro de diálogo Agregar nuevo elemento, seleccione **canalización de envío** desde el panel Plantillas.  

3. En el **nombre** , escriba un nombre para la canalización de recepción, tales como **FRRSendPipeline.btp**. Haga clic en **Agregar**.  

4. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en **vista** y, a continuación, **cuadro de herramientas**.  

5. En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **ensamblador de SWIFT** a la **Coloque aquí** cuadro a continuación el **ensamblar** en forma de organizar **canalizaciones de BizTalk Diseñador**.  

6. En el cuadro de herramientas de componentes de canalización de BizTalk, arrastre **componente de envío de SWIFT Frr MQSeries** a la **Coloque aquí** cuadro a continuación el **Encode** en forma de organizar  **Diseñador de canalizaciones de BizTalk**.  

7. En el Explorador de BizTalk, haga clic en el proyecto de canalización, haga clic en **Undeploy**y, a continuación, haga clic en **Sí**.  

   > [!NOTE]
   >  Después de anular la implementación y, a continuación, volver a implementar el proyecto de canalización, debe restablecer los puertos de envío o ubicaciones de recepción que utilice canalizaciones en el proyecto implementado anteriormente.  

8. En el Explorador de soluciones, haga clic en el proyecto de canalización y, a continuación, haga clic en **compilar**.  

9. Después de la compilación se ha realizado correctamente, haga clic en el proyecto de canalización y, a continuación, haga clic en **implementar**.
