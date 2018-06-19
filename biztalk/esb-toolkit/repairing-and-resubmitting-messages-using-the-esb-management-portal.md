---
title: Reparar y volver a enviar mensajes con el Portal de administración de ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43091cbd-77d1-4cbd-9190-2d423ce7d4df
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61602fb41a2c6754fe6d77d249e2ec8c2f40cd39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295260"
---
# <a name="repairing-and-resubmitting-messages-using-the-esb-management-portal"></a>Reparar y volver a enviar mensajes mediante el Portal de administración de ESB
En este caso de uso, un preconfiguradas puerto de envío utilizará el procesador de error de ESB canalización de envío para recibir un mensaje de error ESB generado por el controlador de excepciones en una orquestación o un mensaje de error generados por el mecanismo de enrutamiento de mensajes de error de Microsoft BizTalk Servidor. El procesador de error de ESB normaliza, enriquecer y lo enruta a la base de datos del Portal de administración de ESB. El portal supervisa la base de datos para los mensajes entrantes de error y puede generar alertas que notifiquen a los usuarios suscritos del error de procesamiento. Un usuario puede abrir el mensaje de error en el portal de Visor de errores, editar el contenido del mensaje y vuelva a enviar el mensaje para el procesamiento, como se muestra en la figura 1.  
  
 ![Reparación de mensajes](../esb-toolkit/media/ch3-repairingmessages.gif "Ch3-RepairingMessages")  
  
 **Figura 1**  
  
 **Reparar y volver a enviar mensajes mediante el Portal de administración de ESB**  
  
 El Portal de administración de ESB incluye como un ejemplo con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso. Proporciona un entorno gráfico completo para editar y volver a enviar mensajes; También es compatible con las alertas, notificaciones y auditoría de reenvío de mensajes.  
  
 Para obtener más información, consulte [trabajar con excepciones y mensajes de error](../esb-toolkit/working-with-exceptions-and-fault-messages.md).