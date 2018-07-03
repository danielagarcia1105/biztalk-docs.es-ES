---
title: El servicio Web de control de excepciones | Microsoft Docs
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
ms.openlocfilehash: a1bcc8146947f5e3cbaf58e31d1f515a055d102c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974309"
---
# <a name="the-exception-handling-web-service"></a>El servicio Web de control de excepciones
El servicio Web de control de excepciones acepta un mensaje de error y lo publica en el Portal de excepciones de ESB. Una aplicación cliente puede crear mensajes de excepción y enviarlas a ESB, donde cualquier controlador configurado para ese tipo de excepción o un controlador genérico, puede procesar la excepción. La principal ventaja de este servicio es que permite entidades fuera de una aplicación de ESB para participar en el mecanismo de control de excepciones de ESB.  
  
 El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contiene dos versiones de este servicio: una versión de ASP.NET (ASMX) y una versión de Windows Communication Foundation (WCF). Los nombres de servicio son **ESB. ExceptionHandlingServices** y **ESB. ExceptionHandlingServices.WCF**, respectivamente, y los servicios exponen un único método:  
  
- **SubmitFault**. Este método toma una instancia de la **FaultMessage** clase y no tiene ningún valor devuelto.  
  
  Para obtener información sobre la forma en que funciona el mecanismo de control de excepciones, vea [usando administración de excepciones de ESB](../esb-toolkit/using-esb-exception-management.md).  
  
> [!NOTE]
>  De forma predeterminada, los servicios Web de control de excepciones no se configuran para que requiera Secure Sockets Layer (SSL) cuando obtiene acceso a los clientes. Debe configurar el servicio para que requiera SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el servidor que hospeda el **ESBExceptions** base de datos uso de IPSec de nivel de red y permisos de lista (ACL) del control de acceso de nivel de archivo adecuado.