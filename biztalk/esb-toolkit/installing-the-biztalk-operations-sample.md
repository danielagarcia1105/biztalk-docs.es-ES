---
title: Instalar el ejemplo de operaciones de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa8fb289e5bb7950f9ad8bca3dac98035bada176
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007317"
---
# <a name="installing-the-biztalk-operations-sample"></a>Instalar el ejemplo de operaciones de BizTalk
El ejemplo de operaciones de BizTalk de Microsoft requiere el servicio de operaciones de BizTalk ESB instalado y configurado. Servicio de operaciones de BizTalk ESB es uno de los servicios de Web de básicos que pueden ser instalados y configuran con la herramienta de configuración de ESB. Para obtener más información acerca de cómo utilizar la herramienta de configuración de ESB, consulte [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx). La ubicación predeterminada del servicio Web de las operaciones de BizTalk es http://localhost/ESB.BizTalkOperationsService/Operations.asmx; Sin embargo, puede cambiarlo en el archivo de configuración de aplicación si implementa el servicio en una ubicación diferente o un servidor remoto.  
  
 Debe instalar el ejemplo de operaciones de BizTalk desde el proyecto de la solución.  
  
 **Para instalar el ejemplo de operaciones de BizTalk**  
  
1.  Abra la solución denominada ESB.BizTalkOperations.Test.Client.csproj desde la carpeta \Source\Samples\BizTalkOperations donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos en Visual Studio.  
  
2.  Use los comandos en el **generar** menú para compilar la solución.