---
title: Instalación del ejemplo de operaciones de BizTalk | Microsoft Docs
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
ms.openlocfilehash: 6a4fa6aeb56c9d5e4ed65e80f0a43c2cdedcf8b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002581"
---
# <a name="installing-the-biztalk-operations-sample"></a>Instalación del ejemplo de operaciones de BizTalk
El ejemplo de operaciones de Microsoft BizTalk requiere el servicio de operaciones de BizTalk ESB instalado y configurado. Servicio de operaciones de BizTalk ESB es uno de los servicios Web de principales que se pueden instalar y configuran mediante la herramienta de configuración de ESB. Para obtener más información sobre cómo usar la herramienta de configuración de ESB, consulte [ http://msdn.microsoft.com/library/jj684558(v=bts.80).aspx ](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx). La ubicación predeterminada del servicio Web de las operaciones de BizTalk es <http://localhost/ESB.BizTalkOperationsService/Operations.asmx>; sin embargo, puede cambiarlo en el archivo de configuración de aplicación si implementa el servicio en una ubicación diferente o un servidor remoto.  

 Debe instalar el ejemplo de operaciones de BizTalk desde el proyecto de solución.  

 **Para instalar el ejemplo de operaciones de BizTalk**  

1. Abra la solución denominada ESB.BizTalkOperations.Test.Client.csproj desde la carpeta \Source\Samples\BizTalkOperations donde instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] ejemplos en Visual Studio.  

2. Use los comandos en el **compilar** menú para compilar la solución.
