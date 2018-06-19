---
title: El Portal de administración de ESB y error mensaje Visor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4a1636c-2e45-4ee5-92c2-81c976582da3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9a6e7272e7b707b6ba7650cfb93506c3a54a00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295212"
---
# <a name="the-esb-management-portal-and-fault-message-viewer"></a>El Portal de administración de ESB y el Visor de mensajes de error
Un componente importante de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] está basado en Web portal que proporciona una amplia gama de excepción características de notificación de alerta y administración; además, actúa como la administración de configuración útil y Universal Description, Discovery and Integration ( Interfaz de registro UDDI). La figura 1 muestra la página principal del portal, que proporciona información general sobre el estado de las aplicaciones que se están ejecutando.  
  
 ![Página principal del portal](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")  
  
 **Figura 1**  
  
 **La página principal del Portal de administración de ESB**  
  
 Los usuarios pueden seleccionar un mensaje de error aparece en el Portal de administración de ESB para ver las propiedades de ambiente y estáticas del error y una lista de los mensajes originales contenida en el mensaje de error, tal como se muestra en la figura 2.  
  
 ![Página de Visor de errores](../esb-toolkit/media/ch4-faultviewerpage.gif "Ch4-FaultViewerPage")  
  
 **Figura 2**  
  
 **La página del Visor de errores de ESB del Portal de administración de ESB**  
  
 Mensajes de error de ESB aparece en el Portal de administración de ESB pueden ser el resultado de un error en los valores del mensaje original cuando se envían para su procesamiento. El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] admite la funcionalidad "reparar y volver a enviar", que permite a los administradores y usuarios para editar mensajes con errores y enviarlos a en rampa para su procesamiento.  
  
 Seleccionar entre el contenido mensajes, se abre la página de vista de mensajes en la vista de detalles del mensaje, tal como se muestra en la figura 3. En esta vista, los usuarios pueden ver el mensaje de contenido, para descargar el mensaje o haga clic en **editar** para cambiar a vista de edición, donde pueden reparar y volver a enviar el mensaje.  
  
 ![Página del Visor de mensajes](../esb-toolkit/media/ch4-messageviewerpage.gif "Ch4-MessageViewerPage")  
  
 **Figura 3**  
  
 **El Visor de mensajes de ESB que muestra la vista de detalles del error**  
  
 Para obtener una descripción completa y las opciones de uso del Portal de administración de ESB, incluidos el Visor de error, el proceso de reenvío de mensajes y las técnicas usadas para obtener una lista, ordenar y analizar los errores, vea [administración de BizTalk ESB Kit de herramientas](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md).