---
title: El servicio Web de control de excepciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfe6ebdf-9b92-40c7-93fb-afd6c5f68aaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8d8f3439e3b99d118e2932d0a158113ec51be2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294956"
---
# <a name="the-exception-handling-web-service"></a>El servicio Web de control de excepciones
El servicio Web de control de excepciones acepta un mensaje de error y lo publica en el Portal de la excepción de ESB. Una aplicación cliente puede crear mensajes de excepción y enviarlos a ESB, donde cualquier controlador configurado para ese tipo de excepción o un controlador genérico, puede procesar la excepción. La principal ventaja de este servicio es que permite a las entidades fuera de una aplicación de ESB para participar en el mecanismo de control de excepciones de ESB.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF). Los nombres de servicio son **ESB. ExceptionHandlingServices** y **ESB. ExceptionHandlingServices.WCF**, respectivamente, y los servicios exponen un método único:  
  
-   **SubmitFault**. Este método toma una instancia de la **FaultMessage** clase y no tiene ningún valor devuelto.  
  
 Para obtener información sobre la forma en que funciona el mecanismo de control de excepciones, vea [utilizando Administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).  
  
> [!NOTE]
>  De forma predeterminada, los servicios Web de control de excepciones no estén configurados para requerir Secure Sockets Layer (SSL) a los que tienen acceso los clientes. Debe configurar el servicio para que requiere SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor que hospeda el **ESBExceptions** base de datos uso de IPSec de nivel de red y permisos de lista (ACL) del control de acceso de nivel de archivo adecuado.