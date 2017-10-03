---
title: "Instalar el ejemplo de MQRFH2 JMS con los Scripts de instalación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 785f3e32-83b4-406a-af1b-9499115fbb8f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27b3606d53f692ff52779eeac3505fd8062bed28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-jms-mqrfh2-sample-using-the-install-scripts"></a>Instalar el ejemplo de MQRFH2 JMS mediante las secuencias de comandos de instalación
En esta sección se describe cómo puede instalar el ejemplo de JMS MQRFH2 mediante los scripts de instalación que se proporcionan con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
 **Para instalar los ejemplos de JMS MQRFH2 desde las secuencias de comandos de instalación**  
  
1.  Mediante el Explorador de WebSphere, cree un administrador de cola con el nombre **ESB. JMS. Sample.QueueManager**.  
  
2.  Mediante el Explorador de WebSphere, cree las siguientes cuatro colas dentro de **ESB. JMS. Sample.QueueManager:**  
  
    -   ESB. JMS. EJEMPLO. DYNAMICQ1  
  
    -   ESB. JMS. EJEMPLO. DYNAMICQ2  
  
    -   ESB. JMS. EJEMPLO. RESPUESTA  
  
    -   ESB. JMS. EJEMPLO. SENDTOBIZTALK  
  
3.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
4.  En el **ejecutar** cuadro de diálogo, escriba **cmd**, y, a continuación, presione ENTRAR.  
  
5.  Ejecute el comando siguiente, reemplazando el  *\<ruta de acceso >* parámetro con la ruta de acceso completa al archivo .cmd que desea instalar (la ruta predeterminada en esta versión es \Source\Samples\JMS\Install\Scripts\\):  
  
    ```  
    <path>\Setup_bin.cmd  
    ```