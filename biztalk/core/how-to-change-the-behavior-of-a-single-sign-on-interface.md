---
title: Cómo cambiar el comportamiento de una interfaz de inicio de sesión único | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4a4946a-e345-4c7e-835d-a3f7f72ebaca
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29f8adf1be531b5d439200dd2a10667ecf72bfbf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000821"
---
# <a name="how-to-change-the-behavior-of-a-single-sign-on-interface"></a>Cómo cambiar el comportamiento de una interfaz de inicio de sesión único
Muchos objetos del modelo de objetos de inicio de sesión único (SSO) empresarial exponen la interfaz IPropertyBag, que permite modificar el comportamiento del objeto especificado. Si llama a QueryInterface en un objeto de SSO, puede recuperar la interfaz IPropertyBag y usarla para cambiar el comportamiento del objeto actual.  

### <a name="to-change-the-behavior-for-a-specified-sso-interface"></a>Para cambiar el comportamiento de una interfaz de SSO especificada  

1.  Use QueryInterface en la interfaz especificada para recuperar una instancia de IPropertyBag.  

2.  Utilice IPropertyBag.Write para establecer la propiedad, el tipo y el valor de la interfaz.  

     En la siguiente tabla se describen los valores válidos para los parámetros propName y ptrVar de IPropertyBag:  

|propName|Tipo|ptrValue|Se puede usar en|  
|--------------|----------|--------------|---------------|  
|CurrentSSOServer|VT_BSTR|Nombre del servidor al que se envía la información.|All|  
|Transaction|VT_UNKNOWN<br /><br /> VT_EMPTY|Puntero ITransaction de DTC o valor NULL para borrar el ámbito.|ISSOConfigStore::SetConfigInfo<br />ISSOConfigStore::GetConfigInfo <br />ISSOConfigStore::DeleteConfigInfo<br /><br /> ISSOAdmin::CreateApplication<br />ISSOAdmin::DeleteApplication <br />ISSOAdmin::UpdateApplication<br />ISSOAdmin::CreateFieldInfo<br /><br /> ISSOMapper::GetFieldInfo|  
|AppFilterFlags|VT_I4<br /><br /> VT_UI4|Marcas para controlar la aplicación que se va a filtrar.|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AppFilterFlagsMask|VT_I4<br /><br /> VT_UI4|Máscara de marca para controlar la aplicación que se va a filtrar.|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AsyncCall|VT_BOOL|True para utilizar una llamada RPC asíncrona; false para usar una llamada RPC sincrónica.|ISSOConfigOM::GetServerStatus<br /><br /> ISSOAdmin::GetGlobalInfo|  

- **CurrentSSOServer**: el comportamiento estándar para determinar qué servidor desea enviar información de inicio de sesión único para es como sigue:  

  1. Buscar el usuario actual en el Registro. Se puede establecer el nombre de servidor para el usuario actual con las herramientas de línea de comandos o la GUI.  

  2. Buscar todos los usuarios en el Registro. Se puede establecer el nombre de servidor para todos los usuarios con las herramientas de línea de comandos o la GUI.  

  3. Si no se encuentra ningún nombre de servidor de SSO en el Registro, usar el equipo actual.  

     Al establecer CurrentSSOServer en un servidor especificado, se invalida el proceso anterior para la interfaz indicada. Tras establecer CurrentSSOServer, todas las llamadas posteriores a métodos que se realicen en la interfaz se enviarán al servidor especificado.  

- **Transacción**: especifica una transacción DTC que, al ámbito de las operaciones realizadas por el inicio de sesión único, modelo de objetos. Debe pasar un puntero ITransaction de DTC en `ptrValue` o un valor "null" para borrar el ámbito de transacción actual.  

- **AppFilterFlags/AppFilterMask**: controla lo que los tipos de aplicaciones que se devolverán ISSOMapper.GetApplications e ISSOMapper2.GetApplications. Si las marcas de aplicación coinciden con las especificadas por las marcas de filtro y la máscara de las marcas de filtro, se devolverán. Una forma de filtrar las aplicaciones consiste en establecer AppFilterFlagsMask en SSO_FLAG_APP_FILTER_BY_TYPE y, a continuación, establecer AppFilterFlags en uno o varios de los siguientes elementos:  

   SSO_APP_TYPE_INDIVIDUAL  

   SSO_APP_TYPE_GROUP  

   SSO_APP_TYPE_CONFIG_STORE  

   SSO_APP_TYPE_HOST_GROUP  

   SSO_APP_TYPE_PS_ADAPTER  

   SSO_APP_TYPE_PS_GROUP_ADAPTER  

- **AsyncCall**: si es true, SSO ejecutará el método mediante una llamada asincrónica de procedimiento remoto (RPC). El método devolverá E_PENDING mientras esté en curso. Si se devuelve cualquier otro valor significa que el método se ha completado. AsyncCall también permite sondear si el método se ha completado.
