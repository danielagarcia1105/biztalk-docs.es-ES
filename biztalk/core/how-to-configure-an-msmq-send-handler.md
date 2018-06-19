---
title: Cómo configurar un controlador de envío MSMQ | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send handlers
- configuring [MSMQ adapters], send handlers
- send handlers, MSMQ adapters
ms.assetid: 21917596-f27a-473b-859e-186ab5f4cd94
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feacaec9d2794cf8806fa5156fe64b7290699faa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248268"
---
# <a name="how-to-configure-an-msmq-send-handler"></a>Cómo configurar un controlador de envío MSMQ
El siguiente procedimiento se utiliza para modificar las variables globales de un controlador de envío MSMQ.  
  
> [!NOTE]
>  Cada host puede tener solo un controlador de envío asociado a él.  
  
### <a name="to-change-global-variables-for-an-msmq-send-handler-by-using-the-biztalk-server-administration-console"></a>Para cambiar variables globales de un controlador de envío MSMQ utilizando la consola de administración de BizTalk Server  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en **MSMQ**, en el panel derecho, haga el controlador de envío que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host con la que asociará el controlador de envío y, a continuación, haga clic en **Propiedades**.  
  
4.  En el **propiedades de transporte de MSMQ** diálogo cuadro, escriba un valor para **tamaño de lote**.  
  
     El controlador de envío MSMQ enviará mensajes a colas de destino utilizando especificado **tamaño de lote** parámetro. El valor predeterminado **tamaño de lote** valor es 5.  
  
5.  Haga clic en **Aceptar** y haga clic en **Aceptar** otra vez para cerrar el **propiedades de controlador de adaptador** cuadro de diálogo.