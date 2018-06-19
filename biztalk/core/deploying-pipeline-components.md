---
title: Implementar componentes de canalización | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, pipeline components [custom]
- pipeline components [custom], deploying
ms.assetid: 98b47fbf-62c0-4012-a406-58c4d56b305a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 041bd8c6e6fa9c3969be18f0804460c00de5f11a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969034"
---
# <a name="deploying-pipeline-components"></a>Implementar componentes de canalización
Todas la canalización componente ensamblados .NET (nativos y personalizados) deben estar ubicados en el \< *directorio de instalación de*\>carpeta \Pipeline Components para ser ejecutado por el servidor. Si la canalización que tiene un componente personalizado se va a implementar en varios servidores, los archivos binarios del componente deben estar presentes en la carpeta especificada de cada servidor.  
  
 No es necesario que agregue un componente de canalización personalizado para que lo use el Tiempo de ejecución de BizTalk en la caché de ensamblados global (GAC).  
  
 Los componentes COM personalizados de la canalización aparecerán en el Cuadro de herramientas, siempre y cuando se registren en el equipo como un componente COM. Componentes de canalización de .NET personalizados se deben colocar en el \< *directorio de instalación de*\>carpeta \Pipeline Components.  
  
 Una vez que los archivos binarios están en la ubicación correcta, es necesario que agregue el componente al Cuadro de herramientas. Para obtener instrucciones sobre cómo agregar el componente de canalización al cuadro de herramientas, consulte [cómo utilizar el cuadro de herramientas](../core/how-to-use-the-toolbox.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de componentes de canalización personalizados](../core/developing-custom-pipeline-components.md)