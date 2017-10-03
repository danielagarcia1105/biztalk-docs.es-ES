---
title: "Solución orientada a servicios de referencia de mensajes para el servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service solution tutorial, message reference
ms.assetid: 47b56d83-799d-444d-b7ef-c2db56a0e470
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d970b34874d893b9c110f360abc27336c4cba80d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="message-reference-for-the-service-oriented-solution"></a>Referencia de los mensajes de la solución orientada a servicios
En esta sección se muestran los mensajes y tipos de mensajes utilizados por cada orquestación de la solución. Los mensajes y los tipos se muestran ordenados por la versión de la aplicación.  
  
## <a name="adapter-version"></a>Versión del adaptador  
 En la tabla, \<Prefijosolución > sustituye a Microsoft.Samples.BizTalk.woodgrovebank para el formato de la tabla simplificar.  
  
 Las orquestaciones, los mensajes y los tipos son los siguientes:  
  
|Orquestación|de mensaje|Tipo de mensaje|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<Prefijosolución >. Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<Prefijosolución >. Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<Prefijosolución >. Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_. GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<Prefijosolución >. Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_. GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<Prefijosolución >. Schemas.BAPI_BANKACCT_GET_DETAIL. BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<Prefijosolución >. Schemas.BAPI_BANKACCT_GET_DETAIL. BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<Prefijosolución >. Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<Prefijosolución >. Schemas.PendingTransactionsResponse|  
|CustomerService.odx|StubSAPWebServiceRequest|\<Prefijosolución >. Orchestrations.Adapter.StubSAPWS.StubSAPWS_. GetAccountDetails_request|  
|CustomerService.odx|StubSAPWebServiceResponse|\<Prefijosolución >. Orchestrations.Adapter.StubSAPWS.StubSAPWS_. GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
  
## <a name="adapter-with-sap-version"></a>Versión del adaptador con SAP  
 En la tabla, \<Prefijosolución > sustituye a Microsoft.Samples.BizTalk.woodgrovebank para el formato de la tabla simplificar.  
  
 Las orquestaciones, los mensajes y los tipos son los siguientes:  
  
|Orquestación|de mensaje|Tipo de mensaje|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<Prefijosolución >. Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<Prefijosolución >. Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<Prefijosolución >. Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_. GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<Prefijosolución >. Orchestrations.Adapter.PendTransWS.PendingTransactionsWebService_. GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<Prefijosolución >. Schemas.BAPI_BANKACCT_GET_DETAIL. BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<Prefijosolución >. Schemas.BAPI_BANKACCT_GET_DETAIL. BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<Prefijosolución >. Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<Prefijosolución >. Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
  
## <a name="inline-version"></a>Versión en línea  
 En la tabla, \<Prefijosolución > sustituye a Microsoft.Samples.BizTalk.WoodgroveBank para ayudar a aplicar formato a la tabla.  
  
 Las orquestaciones, los mensajes y los tipos son los siguientes:  
  
|Orquestaciones|de mensaje|Tipo de mensaje|  
|--------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<Prefijosolución >. Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<Prefijosolución >. Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<Prefijosolución >. Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsWSResponse|\<Prefijosolución >. Schemas.PendingTransactionsResponse|  
|CustomerService.odx|CreditLimitRequest|\<Prefijosolución >. Schemas.BAPI_BANKACCT_GET_DETAIL. BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<Prefijosolución >. Schemas.BAPI_BANKACCT_GET_DETAIL. BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|LastPaymentRequestAfterSendPipeline|System.Xml.XmlDocument|  
|CustomerService.odx|LastPaymentResponseBeforeReceivePipeline|System.Xml.XmlDocument|  
|CustomerService.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse2|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceReceiveSend.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
  
## <a name="stub-version"></a>Versión de código auxiliar  
 En la tabla, \<Prefijosolución > sustituye a Microsoft.Samples.BizTalk.WoodgroveBank para ayudar a aplicar formato a la tabla.  
  
 Las orquestaciones, los mensajes y los tipos son los siguientes:  
  
|Orquestación|de mensaje|Tipo de mensaje|  
|-------------------|-------------|------------------|  
|CustomerService.odx|LastPaymentRequest|\<Prefijosolución >. Schemas.LastPaymentRequest|  
|CustomerService.odx|LastPaymentResponse|\<Prefijosolución >. Schemas.LastPaymentResponse|  
|CustomerService.odx|PendingTransactionsWSRequest|\<Prefijosolución >. Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_. GetPendingTransactions_request|  
|CustomerService.odx|PendingTransactionsWSResponse|\<Prefijosolución >. Orchestrations.Stubbed.StubPendTransWS.StubPendingTransactionsWebService_. GetPendingTransactions_response|  
|CustomerService.odx|CreditLimitRequest|\<Prefijosolución >. Schemas.BAPI_BANKACCT_GET_DETAIL. BAPI_BANKACCT_GET_DETAIL_Request|  
|CustomerService.odx|CreditLimitResponse|\<Prefijosolución >. Schemas.BAPI_BANKACCT_GET_DETAIL. BAPI_BANKACCT_GET_DETAIL_Response|  
|CustomerService.odx|PendingTransactionsRequest|\<Prefijosolución >. Schemas.PendingTransactionsRequest|  
|CustomerService.odx|PendingTransactionsResponse|\<Prefijosolución >. Schemas.PendingTransactionsResponse|  
|CustomerService.odx|PaymentTrackerWSRequest|\<Prefijosolución >. Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_. GetLastPayments_request|  
|CustomerService.odx|PaymentTrackerWSResponse|\<Prefijosolución >. Orchestrations.Stubbed.StubPmntTrckWS.StubPaymentTrackerWebService_. GetLastPayments_response|  
|CustomerService.odx|StubSAPWSRequest|\<Prefijosolución >. Orchestrations.Stubbed.StubSAPWS.StubSAPWS_. GetAccountDetails_request|  
|CustomerService.odx|StubSAPWSResponse|\<Prefijosolución >. Orchestrations.Stubbed.StubSAPWS.StubSAPWS_. GetAccountDetails_response|  
|CustomerService.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
|CustomerService.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceRequest|\<Prefijosolución >. Schemas.CustomerServiceRequest|  
|CustomerServiceNativeRequestResponse.odx|CustomerServiceResponse|\<Prefijosolución >. Schemas.CustomerServiceResponse|  
  
## <a name="see-also"></a>Vea también  
 [Referencia de la solución orientada a servicios](../core/service-oriented-solution-reference.md)