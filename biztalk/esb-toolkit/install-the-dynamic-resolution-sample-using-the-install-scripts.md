---
title: Instalar el ejemplo de resolución dinámica con los Scripts de instalación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 644b6403-9883-4256-80d5-37881a87ed0e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 872bb73b9060e25986876c1c2da71afae84b5c52
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973146"
---
# <a name="install-the-dynamic-resolution-sample-using-the-install-scripts"></a>Instalar el ejemplo de resolución dinámica con los Scripts de instalación
En esta sección se describe cómo puede instalar el ejemplo de resolución dinámica de las secuencias de comandos de instalación proporcionadas con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
 **Para instalar el ejemplo de resolución dinámica de las secuencias de comandos de instalación**  
  
1.  Si desea ejecutar los ejemplos de mensajes unidireccionales que utilicen FTP, cree el siguiente sitio FTP:  
  
    -   Nombre del directorio Virtual FTP: Out  
  
    -   Ubicación: \Source\Samples\DynamicResolution\Test\FTP\Out  
  
    -   Permisos: Lectura y escritura  
  
    -   Asegúrese de que el grupo de usuarios de la aplicación de BizTalk tiene permiso de acceso completo para esta ubicación  
  
2.  Si desea ejecutar los ejemplos de mensajes bidireccionales que usan MQSeries, utilice el Explorador de WebSphere para crear lo siguiente:  
  
    -   Un administrador de cola con el nombre ESB. USO DE DEP. Sample.QueueManager  
  
    -   Una cola denominada TEST. OUT dentro de ESB. USO DE DEP. Sample.QueueManager  
  
3.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
4.  En el **ejecutar** cuadro de diálogo, escriba **cmd**, y, a continuación, presione ENTRAR para abrir el símbolo del sistema.  
  
5.  Ejecute el comando siguiente, reemplazando el \<ruta de acceso\> parámetro con la ruta de acceso completa al archivo .cmd que desea instalar (la ruta predeterminada en esta versión es \Source\Samples\DynamicResolution\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```