---
title: Instalar el ejemplo de operaciones de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c982c2-f796-4c63-9bca-7e8965779850
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6307f9d9e4ff9907bab22efcde0755dbdfdc228b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-biztalk-operations-sample"></a>Instalar el ejemplo de operaciones de BizTalk
El ejemplo de operaciones de BizTalk de Microsoft requiere el servicio de operaciones de BizTalk ESB instalado y configurado. Servicio de operaciones de BizTalk ESB es uno de los servicios de Web de básicos que pueden ser instalados y configuran con la herramienta de configuración de ESB. Para obtener más información acerca de cómo utilizar la herramienta de configuración de ESB, consulte [http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx). La ubicación predeterminada del servicio Web de las operaciones de BizTalk es http://localhost/ESB.BizTalkOperationsService/Operations.asmx; Sin embargo, puede cambiarlo en el archivo de configuración de aplicación si implementa el servicio en una ubicación diferente o un servidor remoto.  
  
 Debe instalar el ejemplo de operaciones de BizTalk desde el proyecto de la solución.  
  
 **Para instalar el ejemplo de operaciones de BizTalk**  
  
1.  Abra la solución denominada ESB.BizTalkOperations.Test.Client.csproj desde la carpeta \Source\Samples\BizTalkOperations donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos en [!INCLUDE[vs2010](../includes/vs2010-md.md)].  
  
2.  Use los comandos en el **generar** menú para compilar la solución.