---
title: Publicando el archivo de instancia de mensaje MX (creación de mensajes) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7e6cdf4-b9db-42be-a92d-10a7471e2c2d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c7894158bb245b746b9a53dcfc93d40b9f9e1d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970685"
---
# <a name="publishing-the-mx-message-instance-file-creating-new-messages"></a>Publicando el archivo de instancia de mensaje MX (creación de mensajes)
**Para publicar el archivo de instancia de mensaje MX:**  

1. Vaya a la carpeta de salida de la plantilla de formulario de InfoPath generada en el paso anterior **... \\< MessageType\>\TemplateDS\InfoPath plantilla**.  

2. En Internet Explorer, abra **http://localhost/sites/BASSite/New%20SWIFT%20MX%20Messages**.  

3. En la ventana de nuevos mensajes de Swift MX, haga clic en **cargar**.  

4. En la ventana Cargar documento, haga clic en **examinar**.  

5. En el cuadro de diálogo Elegir archivo, mover a la carpeta de salida del formulario de InfoPath generado en el paso anterior **... \\< MessageType\>\TemplateDS\InfoPath plantilla**. Seleccione el \<MessageType\>como pacs.004.001.01.xml de archivos .xml y, a continuación, haga clic en **abierto**.  

6. En la ventana Cargar documento, haga clic en **Aceptar**.  

7. En los mensajes de nuevo MX SWIFT: \<MessageType\> ventana, en el cuadro de Namespace, escriba <strong>http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageType\></strong>y, a continuación, haga clic en **Aceptar**.
