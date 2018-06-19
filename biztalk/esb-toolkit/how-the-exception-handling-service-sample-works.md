---
title: Cómo funciona el ejemplo de servicio de control de excepciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d095752-e212-42bf-9559-efa14d2ad09c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eac3a9ff96025f5248c0434a69c38eb01a704488
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22293924"
---
# <a name="how-the-exception-handling-service-sample-works"></a>Cómo funciona el ejemplo de servicio de control de excepciones
El ejemplo de servicio de control de excepciones es una aplicación de formularios Windows Forms de .NET estándar que contiene a un proxy de servicio generado para el servicio de control de excepciones. La aplicación consta de un único formulario con un solo botón, **generar excepciones**. Al hacer clic en este botón, una instancia de la **FaultMessage** se genera la clase. El **FaultMessage** es una clase que fue generada por Microsoft Visual Studio basado en el lenguaje de descripción de servicios de Web (WSDL) proporcionada por el servicio Web de control de excepciones. Las propiedades de esta instancia se rellenan con valores predeterminados que simulan un error que se producen en una aplicación externa antes de que las propiedades se pasan como parámetros a la **SubmitFault** método de Web de control de excepciones servicio.  
  
 Para obtener más información acerca de cómo funciona el servicio Web de control de excepciones, vea [control de servicio Web de la excepción](../esb-toolkit/the-exception-handling-web-service.md).