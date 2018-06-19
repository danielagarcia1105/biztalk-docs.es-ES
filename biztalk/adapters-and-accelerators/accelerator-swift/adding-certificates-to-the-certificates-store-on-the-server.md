---
title: Agregar certificados al almacén de certificados en el servidor | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 075cfae8-dce7-46f7-9539-796f03229ea2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94661568108e5a1cc05140a97c933fb8d00e3c67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209572"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a>Agregar certificados al almacén de certificados en el servidor
Siga estos pasos para agregar certificados a la carpeta de otras personas en el almacén de certificados (equipo Local) en el equipo del servidor.  
  
### <a name="to-add-certificates-to-the-certificate-store"></a>Para agregar certificados al almacén de certificados  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **Acelerador de BizTalk para SWIFT administración Consola**.  
  
    > [!NOTE]
    >  Si sigue teniendo la ventana MMC abrir desde el procedimiento anterior (agregar certificados al almacén de certificados en el cliente), puede utilizarlo para este procedimiento.  
  
2.  En la ventana de consola de administración, expanda la **certificados (equipo Local)** carpeta y, a continuación, expanda **otras personas**.  
  
3.  Haga clic en **certificados**, seleccione **todas las tareas**y, a continuación, haga clic en **importación**.  
  
4.  En la página Asistente para la página del Asistente para importación de certificados, haga clic en **siguiente**.  
  
5.  En la página archivo para importar, haga clic en **examinar**.  
  
6.  En el cuadro de diálogo Abrir, mover a la ubicación del archivo donde se guardó el certificado, seleccione **todos los archivos** para **archivos es de tipo**, seleccione el certificado que desea importar y, a continuación, haga clic en  **Abra**.  
  
7.  En la página archivo para importar, haga clic en **siguiente**.  
  
8.  En la página almacén de certificados, compruebe que **colocar todos los certificados en el siguiente almacén** está seleccionado, compruebe que **otras personas** se muestra en el **el almacén de certificados**cuadro y, a continuación, haga clic en **siguiente**.  
  
9. En la página Finalización la página del Asistente para importación de certificados, haga clic en **finalizar**.  
  
10. En el cuadro de diálogo del Asistente para importar certificados que indica una importación correcta, haga clic en **Aceptar**.  
  
11. Repita los pasos del 3 al 10 para el resto de los certificados que se va a utilizar en la reparación de mensajes y nuevo envío.