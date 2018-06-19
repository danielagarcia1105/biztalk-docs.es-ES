---
title: Agregar un puerto de envío MX | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3ad5d2f-1fcb-49d4-9974-664733308f45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cd4c16658ad0ff6b85976fbc6a97c4f397acbdb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208916"
---
# <a name="adding-an-mx-send-port"></a>Agregar un puerto de envío de MX
**Para agregar un puerto de envío MX:**  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, en el cuadro Nombre tipo **MX_SendPort**.  
  
3.  En la sección transporte, en el cuadro Tipo, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
4.  Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.  
  
5.  En el cuadro de diálogo Propiedades de transporte de archivo, haga clic en **examinar**.  
  
6.  En el cuadro de diálogo carpeta buscar, seleccione una ubicación de archivo.  
  
7.  En el cuadro de nombre de archivo, escriba **%MessageID%.xml**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Propiedades de puerto de envío, haga clic en la lista desplegable del cuadro de la canalización de envío y, a continuación, seleccione la canalización de envío que haya implementado en el proyecto de canalización.  
  
9. En el panel izquierdo, haga clic en **filtros**y, a continuación, especifique lo siguiente:  
  
    |||  
    |-|-|  
    |Propiedad|Microsoft.Solutions.MX_A4SWIFT. Property.MX_A4SWIFT_Failed|  
    |Operador|Seleccione ==|  
    |Valor|False|  
  
10. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.  
  
11. En el panel de puertos de envío, haga clic en **MX_SendPort**y, a continuación, haga clic en **iniciar**.