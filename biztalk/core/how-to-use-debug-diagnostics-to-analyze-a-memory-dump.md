---
title: Cómo usar diagnósticos de depuración para analizar un volcado de memoria | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 986a91a7-feab-4014-bbd5-e8b966b8b841
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc0faf72c9123ab7a501af8520f273e8c528b8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256604"
---
# <a name="how-to-use-debug-diagnostics-to-analyze-a-memory-dump"></a>Cómo usar diagnósticos de depuración para analizar un volcado de memoria
El diagnóstico de IIS **Debug Diagnostics Tool** incluye una característica que puede proporcionar un análisis básico de un archivo de volcado de memoria capturado. Para realizar un análisis de un archivo de volcado de la memoria, siga estos pasos.  
  
### <a name="to-analyze-the-dump-file"></a>Para analizar el archivo de volcado  
  
1.  Inicie la herramienta de diagnósticos de depuración desde **iniciar**, **programas**, **IIS Diagnostics**, **Debug Diagnostics Tools**,  **Herramienta de diagnóstico 1.0 de depuración**.  
  
2.  Haga clic en el **análisis avanzado** ficha.  
  
3.  En **secuencias de comandos de análisis disponibles** haga clic para seleccionar **analizadores de bloqueo/bloqueo** para analizar un volcado de bloqueo o dejar de responder o haga clic para seleccionar **análisis de presión de memoria** para analizar un objeto de memoria volcado de memoria de un proceso parece que pierde memoria.  
  
4.  Haga clic en el **agregar archivos de datos** botón para buscar el archivo de volcado de memoria generado y haga clic en el **abiertos** botón para agregar el archivo de volcado de memoria a la lista de posibles de archivos de datos que se va a analizar.  
  
5.  Haga clic para seleccionar el archivo de volcado que se ha agregado.  
  
6.  Haga clic en el **iniciar análisis** botón.  
  
    > [!NOTE]
    >  El analizador intentará localizar y descargar los archivos de símbolos adecuados de Internet si no están instalados en el equipo local. Si se ejecuta código personalizado en el proceso BTSNTSvc.exe, actualice el **símbolo Buscar ruta de acceso para la depuración** opción disponible en la **rutas de búsqueda y de carpeta** pestaña de la **opciones & Configuración de** cuadro de diálogo para incluir los archivos de símbolos adecuados. Haga clic en el **herramientas** menú y seleccione **opciones y configuración** para mostrar la **opciones y configuración** cuadro de diálogo.  
  
7.  Una vez completado el análisis, se genera un informe en formato de archivo .mht y se muestra en Internet Explorer. De forma predeterminada, este informe se guardará en el directorio \Archivos de programa\IIS Resources\DebugDiag\Reports del equipo local.  
  
## <a name="see-also"></a>Vea también  
 [Cómo capturar un volcado de memoria de un proceso de BizTalk](../core/how-to-capture-a-memory-dump-of-a-biztalk-process.md)