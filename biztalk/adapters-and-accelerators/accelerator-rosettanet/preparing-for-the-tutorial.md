---
title: Requisitos previos para el tutorial de RosettaNet Loopback en BizTalk Server | Documentos de Microsoft
description: Requisitos previos para recorrer el tutorial de bucle invertido para el Acelerador para RosettaNet (BTARN) en BizTalk Server
caps.latest.revision: "9"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e26696c-86c5-448b-9cd6-bfd4a279151a
ms.author: mandia
ms.openlocfilehash: 9767f7823e80d4de67345ba0fbf59c1435adb8e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-for-the-tutorial"></a>Prepararse para el tutorial

## <a name="prerequisites"></a>Requisitos previos
Antes de iniciar el tutorial de bucle invertido:
  
-   [Instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md) el acelerador. Tendrá que agregar el directorio virtual btarnhttpreceive a la lista de exclusión de la ruta de acceso administrada de Windows SharePoint en Administración Central de SharePoint.  
  
-   Asegúrese de que los hosts BizTalkServerIsolatedHost y AplicaciónBizTalkServer tienen la **autenticación de confianza** opción habilitada. Para comprobar, abra la consola de administración de BizTalk Server y expanda **Hosts**. Haga clic en el host, seleccione **propiedades**y compruebe **autenticación de confianza** si no está habilitado.  

    Si tiene más de una instancia de host, a continuación, elimine todo menos una instancia de host. Por ejemplo, elimine la instancia de Host aislado de BizTalk Server y mantener la instancia de host BizTalkServerApplication). Este permite seleccionar **autenticación de confianza** en el host asociado a la instancia y, a continuación, volver a crear las instancias de host adicionales.  
  
## <a name="next-step"></a>Paso siguiente
 [Paso 1: Crear la organización principal](step-1-create-the-home-organization.md)