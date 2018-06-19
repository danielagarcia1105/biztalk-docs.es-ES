---
title: Página de configuración de error | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f10b8b-9a32-40ca-9ce4-0b69e159c36c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ce03e5284122e8c1de9bd4e5c2d69c392174e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294148"
---
# <a name="fault-settings-page"></a>Página de configuración de error
La figura 1 muestra la página de configuración de error. Esta página muestra una variedad de opciones administrativas que se pueden modificar.  
  
 ![Página de configuración de error](../esb-toolkit/media/ch8-faultsettingspage.gif "Ch8-FaultSettingsPage")  
  
 **Figura 1**  
  
 **La página de configuración de error del Portal de administración de ESB**  
  
 En la lista siguiente se explica cómo puede usar las características de la página de configuración de error del Portal de administración de ESB:  
  
-   Para cambiar las opciones de auditoría, active las casillas de verificación para cada evento que desea auditar. Los eventos disponibles son la posibilidad de guardar la configuración modificada, reenvío correcto de un error después de modificarlo y error al volver a enviar un error.  
  
-   El portal mantiene una cola de las alertas generadas por el servicio de alertas del Portal. Puede modificar la configuración para este servicio en la **opciones de alerta de cola** sección de la página. Puede habilitar o deshabilitar el servicio, especifique su interacción con el servicio de directorio de Microsoft Active Directory y controlar el tamaño de lote de cola y el intervalo de sondeo.  
  
-   Para cambiar la configuración para el servicio de correo electrónico de alerta, use los controles en el **opciones de alerta de correo electrónico** sección de la página. Puede habilitar o deshabilitar el servicio; Especifique el servidor de correo electrónico y la dirección "de"; cambiar el tamaño de lote y de intervalo de sondeo; y especifique la ruta de acceso a los archivos XSLT que usa el servicio.  
  
> [!NOTE]
>  Debe escribir los valores en esta página cuando instala y configura el Portal de ESB y el servicio de alertas del Portal. Para obtener más información, consulte [instalar el Portal de administración de ESB](http://go.microsoft.com/fwlink/?LinkId=188554).