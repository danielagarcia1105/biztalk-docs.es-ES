---
title: "Portal de errores de página | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b11e3492-da1a-43f3-acf8-3775b5cbc2c5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 294ba24516cccbf6c15ada26d28f169a6eb45c98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="portal-faults-page"></a>Portal errores de página
La figura 1 muestra la página de errores. Esta página muestra las propiedades principales de cada error, así como ordenar y filtrar las capacidades que admiten un análisis detallado de los errores en un intervalo de criterios, como el tipo de error y la hora. Un vínculo para cada error le permite ver más detalles en el Visor de mensajes de error.  
  
 ![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")  
  
 **Figura 1**  
  
 **La página de errores del Portal de administración de ESB**  
  
 En la lista siguiente se explica cómo puede usar las características de la página de errores de Portal de administración de ESB:  
  
-   Para filtrar la lista de errores que se muestran en la página, use las listas desplegables y cuadros de texto situado encima de la lista de errores. Puede filtrar las filas que se muestran en las siguientes maneras:  
  
    -   Seleccione cualquiera de las aplicaciones de BizTalk instaladas en el **aplicación** lista desplegable.  
  
    -   Especifique el período dentro del cual se produjo el error seleccionando **hora, día, semana, mes, trimestre, año,** o **todos los** en el **recuperar registros dentro de la última** lista desplegable.  
  
    -   Especifique el número de filas que desea mostrar en la página en el **registros por página** lista desplegable.  
  
    -   Escriba un número de código de error en la **código de error** cuadro de texto.  
  
    -   Escriba todo o parte del nombre de categoría de error en la **categoría de error** cuadro de texto.  
  
    -   Escriba todo o parte del texto del tipo de error en la **tipo de Error** cuadro de texto.  
  
    -   Escriba un valor para la gravedad de error mínimos y máximos (como **advertencia, Error, grave,** o **crítico**) en el **gravedad de error Min** y **Max Fault Gravedad** cuadros de texto.  
  
-   Después de especificar los valores para uno o varios de estos controles, haga clic en el **aplicar filtros** botón para aplicar todos los criterios especificados.  
  
-   Haga clic en un encabezado de columna para mostrar las filas de mensaje de error en el orden de ese contenido de la columna y, a continuación, haga clic en nuevo para mostrar la lista en orden inverso.  
  
-   Para mostrar más detalles acerca de un error que se muestra en la lista, o para editar y volver a enviar el mensaje que contiene, haga clic en cualquier parte en la fila para ese error abrirlo en el [Visor de mensajes de error de Portal](../esb-toolkit/portal-fault-message-viewer.md).