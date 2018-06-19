---
title: 'Advertencia: XSLT personalizado pero no hay XML de extensión personalizada | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customXsltButNoCustomExtensionXML
ms.assetid: af008ac2-e9ae-4753-a5ba-bf4dbb711a4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b67591e0e0dbb6b3ecac9aee1566c3245c9969a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288364"
---
# <a name="warning---custom-xslt-but-no-custom-extension-xml"></a>Advertencia: XSLT personalizado pero no hay XML de extensión personalizada
**Código de error**  
  
 btm1034  
  
 **Explicación**  
  
 El **ruta de XSLT personalizada** ha reemplazado la propiedad sin el **XML de extensión personalizada** que se reemplazara propiedad. Si esto sucede de forma intencionada, puede pasar por alto esta advertencia.  
  
 El asignador de BizTalk utilizará el XSLT especificado por el **ruta de XSLT personalizada** propiedad y generar un archivo de asignación de XML de extensión ficticio. Si realiza llamadas a ensamblados externos desde el XSLT personalizado proporcionado, debe especificar un archivo mediante la **XML de extensión personalizada** propiedad que contiene el prefijo de asignación de nombre de ensamblado.  
  
 **Acción del usuario**  
  
 Si la condición indicada por esta advertencia no era intencionada, escriba un valor compatible para la **XML de extensión personalizada** propiedad o quite la invalidación del valor para el **ruta de XSLT personalizada** propiedad.