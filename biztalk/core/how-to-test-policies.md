---
title: Cómo probar directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7a0f8c0d63d14d5a529039a6e1c8af5b363cc9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255812"
---
# <a name="how-to-test-policies"></a>Cómo probar las directivas
Para probar una directiva, necesita hechos en los que se puedan ejecutar las reglas. Puede agregar hechos especificando valores en documentos XML o tablas de bases de datos a las que hará referencia en el comprobador de directivas, o puede utilizar un creador de hechos para suministrar al motor una matriz de objetos .NET como hechos. Para obtener más información, consulte [crear un creador de hechos](../core/how-to-create-a-fact-creator.md).  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a>Para probar una directiva en el Compositor de reglas de negocio  
  
1.  En la ventana Explorador de directivas, haga clic en la versión de directiva que desee probar.  
  
2.  Haga clic en el **probar directiva** botón (flecha verde) en la barra de menús.  
  
     El panel superior muestra los tipos de hechos a los que hacen referencia las reglas de directiva.  
  
3.  Para agregar una instancia de hechos, haga clic en un **documento XML** o **tabla de base de datos** tipo de datos y, a continuación, haga clic en **Agregar instancia**.  
  
4.  Si desea quitar una instancia de hechos, haga clic en el tipo de hechos correspondiente y, a continuación, haga clic en **quitar instancia**.  
  
5.  Si desea agregar un creador de hechos que haya terminado de escribir, haga clic en **agregar** en el panel del creador de hechos.  
  
6.  Haga clic en **prueba**.  
  
     Aparece el resultado del seguimiento de pruebas de directivas en la ventana de resultados de la prueba.  
  
7.  Haga clic con el botón secundario en la ventana de resultados para guardar, borrar, seleccionar o copiar el texto de salida.  
  
     ![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")  
Seleccionar un hecho para probar una directiva