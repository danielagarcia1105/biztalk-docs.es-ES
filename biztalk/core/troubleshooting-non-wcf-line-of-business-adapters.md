---
title: Solución de problemas no - línea de negocio adaptadores de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d5f7877-656f-406e-9edb-d6b9a0705b02
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ba36ed8a8efb62e2eb8e885791c3c28012dcc49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279748"
---
# <a name="troubleshooting-non-wcf-line-of-business-adapters"></a>Solución de problemas de adaptadores de línea de negocio distintos de WCF
## <a name="failed-to-retrieve-error"></a>Error al recuperar  
 Si se usa un adaptador de línea de negocio (LOB) distinto de WCF, se pueden producir los errores siguientes:  
  
-   Error al recuperar el sistema  
  
-   Agente de exploración: ha registrado un Error en el constructor. El equipo de destino rechazó la conexión.  
  
-   Agente de tiempo de ejecución: ha registrado un Error en el constructor. El equipo de destino rechazó la conexión.  
  
### <a name="cause"></a>Causa  
 Los adaptadores de LOB usan las características remotas de .Net. Si la activación de las características remotas de .Net tarda más de lo previsto, puede que el adaptador devuelva estos errores.  
  
### <a name="resolution"></a>Solución  
 Crear el **StartAgentSleep** clave del registro y aumente el valor de tiempo de espera:  
  
1.  Abra el registro y vaya a *HKEY_LOCAL_MACHINE\software\Microsoft\BizTalkAdapters*.  
  
2.  Cree un valor de DWORD nuevo con las propiedades siguientes:  
  
     Nombre: StartAgentSleep  
  
     Base: Decimal  
  
     Datos del valor: 1000  
  
 El valor de datos se mide en milisegundos (ms). 1000 ms equivalen a 1 segundo.  
  
 En algunos sistemas, puede que un segundo no sea suficiente. Aumente el valor y haga pruebas para determinar el tiempo de espera necesario.  
  
> [!IMPORTANT]
>  Agregar el **StartAgentSleep** impactos de clave del registro **todos los** los adaptadores de LOB distintos de WCF.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de adaptadores de BizTalk Server](../core/troubleshooting-biztalk-server-adapters.md)