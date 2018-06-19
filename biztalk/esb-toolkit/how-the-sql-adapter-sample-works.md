---
title: Cómo funciona el ejemplo del adaptador SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77811152-cc8e-4090-89eb-e3a402a46e5e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ff56f2f2f88d35290ffd897d107910e206ac98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294012"
---
# <a name="how-the-sql-adapter-sample-works"></a>Cómo funciona el ejemplo del adaptador SQL
El ejemplo del adaptador de SQL proporciona un itinerario bidireccional de ejemplo configurado con el servicio de enrutamiento y un servicio de mensajería de transformación.  
  
 El servicio de enrutamiento se configura con una resolución estática, que especifica que se debería enrutar el mensaje para ejecutar un procedimiento almacenado de SQL en la base de datos de GlobalBankESB denominado InsertProduct mediante el proveedor del adaptador de WCF-Custom.  
  
 El servicio de transformación especifica una asignación que convierte el mensaje entrante en el formato admitido por el procedimiento almacenado de InsertProduct.