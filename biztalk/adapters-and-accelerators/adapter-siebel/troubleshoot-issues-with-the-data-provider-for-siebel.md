---
title: Solucionar problemas relacionados con el proveedor de datos para Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, troubleshooting
- troubleshooting, Data Provider for Siebel
ms.assetid: 2bfe69a2-d6de-466d-9f36-f11c386c771c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6e100635b1cb2db5c78ff713c8e6ad32d4e7d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222004"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-siebel"></a>Solucionar problemas relacionados con el proveedor de datos para Siebel
Esta sección describe el uso de técnicas de solución de problemas para resolver los errores que pueden surgir al usar el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).  
  
## <a name="known-issues"></a>Problemas conocidos  
  
### <a name="data-provider-for-siebel-may-give-component-datareader-source-380-error"></a>Proveedor de datos para Siebel puede provocar el error de "componente"DataReader, origen' (380)"  
 **Problema**  
  
 Al realizar una consulta SELECT en un componente de negocio de Siebel, el [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] puede provocar un error de "componente"DataReader, origen' (380)".  
  
 **Causa**  
  
 El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] da como resultado de este error si el valor recibido desde el sistema Siebel para un parámetro supera la propiedad maxLength para el parámetro.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)