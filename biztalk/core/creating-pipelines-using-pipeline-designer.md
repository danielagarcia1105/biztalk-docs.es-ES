---
title: Crear canalizaciones mediante el Diseñador de canalizaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, processing messages
- pipelines, Pipeline Designer
- Pipeline Designer, about Pipeline Designer
ms.assetid: 858302d8-a912-4199-95e5-4322db789b4e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b693a4e8df20a7f39f81fb820810c1191ef637
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238052"
---
# <a name="creating-pipelines-using-pipeline-designer"></a>Crear canalizaciones mediante el Diseñador de canalizaciones
Microsoft BizTalk Server trabaja principalmente con el formato de documentos XML. Para que un mensaje pueda sacar el máximo partido del procesamiento del servidor BizTalk Server, a menudo hay que realizar una conversión de su formato nativo a su equivalente XML. Las canalizaciones del servidor BizTalk Server llevan a cabo esta conversión, así como otras acciones relacionadas específicamente con datos (como cifrado o descifrado de datos, promoción de propiedades, etc.) en mensajes entrantes y salientes. En esta sección se proporciona información conceptual y específica de tareas sobre las canalizaciones y el Diseñador de canalizaciones.  
  
 El objetivo de una canalización es preparar un mensaje para que el servidor lo procese una vez que un adaptador lo ha recibido o preparar un mensaje para enviarlo una vez que el servidor lo ha procesado.  
  
 Las canalizaciones suelen llevar a cabo:  
  
-   Normalización de datos de varios formatos a XML.  
  
-   Transformación de datos de XML a varios formatos.  
  
-   Promoción y degradación de propiedades  
  
-   Desensamblado y ensamblado de documentos.  
  
-   Descodificación y codificación de documentos.  
  
-   Descifrado y cifrado de documentos.  
  
-   Comprobación de firma digital y firma de documentos.  
  
 La ilustración que aparece a continuación muestra el flujo de trabajo que conlleva el procesamiento de un mensaje mediante canalizaciones.  
  
 ![Diagrama de flujo de trabajo para procesar un mensaje. ] (../core/media/ebiz-dev-busprcsadptc.gif "ebiz_dev_busprcsadptc")  
Representación del flujo de trabajo de procesamiento de mensajes.  
  
 Como se observa en la ilustración, el mensaje se pasa del adaptador a la canalización de recepción, donde se convierte en XML. A continuación, el mensaje puede ser utilizado por orquestaciones o pasado a una canalización de envío y, seguidamente, a un adaptador de envío.  
  
 Para obtener información sobre cómo usar métodos abreviados de teclado para el Diseñador de canalizaciones, consulte [métodos abreviados de teclado del Diseñador de canalización](../core/pipeline-designer-keyboard-shortcuts.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Acerca de las canalizaciones, fases y componentes](../core/about-pipelines-stages-and-components.md)  
  
-   [Utilizando el Diseñador de canalizaciones](../core/using-pipeline-designer.md)  
  
-   [Crear canalizaciones con el Diseñador de canalizaciones](../core/creating-pipelines-with-pipeline-designer.md)  
  
-   [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)  
  
-   [Cómo implementar canalizaciones](../core/how-to-deploy-pipelines.md)  
  
-   [Cómo proteger canalizaciones](../core/how-to-secure-pipelines.md)