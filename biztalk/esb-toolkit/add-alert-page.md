---
title: "Agregar página alerta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0023ee8d-a0d1-4257-95c6-38c95060bd62
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa93a777481c905dbedfffe5e7675335c4aec40b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="add-alert-page"></a>Agregar página alerta
La figura 1 muestra la página Agregar alerta, donde puede crear una nueva alerta, se producirá el portal cuando llega un mensaje de error que cumpla los criterios (condiciones) especificados en la alerta en el portal.  
  
 ![Agregar página alerta](../esb-toolkit/media/ch8-addalertpage.gif "Ch8-AddAlertPage")  
  
 **Figura 1**  
  
 **La página de ESB Management Portal Agregar alerta**  
  
 En la página Agregar alerta, puede hacer lo siguiente:  
  
-   Escriba un nombre para la nueva alerta en el **escriba el nombre de alerta** cuadro de texto.  
  
-   Especificar cómo se comparará la alerta a valores de los campos de entrada excepciones en el **agregar condiciones para esta alerta** sección de esta página. Seleccione un campo en el esquema de excepción (como **aplicación, tipo de Error,** o **gravedad de error)** en el **criterios** lista desplegable; seleccione un tipo de comparación para el (por ejemplo, como =, **! =, > =, < =,** o **como**) en el **operador** lista desplegable y escriba o seleccione un valor de la tercera lista. Cuando se selecciona un campo de excepción, el **valor** control cambia a un cuadro de texto o una lista desplegable para que escriba o seleccione un valor coincidente.  
  
-   Después de seleccionar o escribir los valores de criterios, haga clic en el **agregar** el vínculo para agregar esta condición a la lista en la **condiciones** sección de la página y repetir para agregar cualquier más condiciones que necesite para esta alerta .  
  
-   Haga clic en el **guardar** botón para crear la nueva alerta con el nombre y las condiciones especificadas.