#### **👉 [자세한 설명은 블로그 보러가기](https://geminii01.github.io/posts/upstage%EC%9D%98-document-parse%EC%99%80-solar-pro-2%EB%A1%9C-rag-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0/)**

## **들어가며**

수십, 수백 페이지에 달하는 PDF 문서를 하나하나 넘겨보면서, 원하는 정보를 찾기 위해 헤맨 경험이 있으신가요? 이러한 검색 방식은 시간을 낭비할 뿐만 아니라, 필요한 정보는 놓치고 단편적인 내용에만 집중하게 될 수 있습니다.

본 튜토리얼에서는 **Document Parse**로 PDF 문서에서 텍스트를 추출하는 방법과 **Solar Pro 2**로 질문에 대해 정확한 답변을 생성하는 RAG 시스템을 함께 구현하면서, **Upstage**의 AI 모델들을 활용하는 것을 배울 수 있습니다.

### **RAG(Retrieval-Augmented Generation)란 무엇일까요?**

RAG는 LLM이 답변을 생성하기 전에, 먼저 외부 DB나 문서에서 관련 정보를 검색하여 그 내용을 기반으로 답변의 근거를 마련해 정확성과 신뢰도를 높이는 방식입니다. 이를 통해 LLM이 잘못된 정보를 생성하는 환각(Hallucination)을 크게 줄일 수 있습니다.

본 튜토리얼에서는 다음 3단계의 절차를 통해 RAG 시스템을 구현합니다.

1. **Indexing** : **Document Parse**를 사용해 PDF와 같은 문서를 불러와서 작은 단위의 청크로 나누고, 이를 벡터로 변환한 후 데이터베이스에 저장합니다.
2. **Retrieval** : 사용자 질문과 가장 유사한 문서 청크들을 검색합니다.
3. **Generation** : 검색된 정보를 참고 자료로 활용하여, 사용자 질문과 함께 **Solar Pro 2**에 전달하여 답변을 생성합니다.

### **References**

- [Build a Retrieval Augmented Generation (RAG) App: Part 1](https://python.langchain.com/docs/tutorials/rag/)
- [What is RAG (Retrieval-Augmented Generation)?](https://aws.amazon.com/what-is/retrieval-augmented-generation/)
- [Upstage Docs: Document Parse](https://console.upstage.ai/docs/capabilities/document-digitization/document-parsing)
- [복잡한 문서를 지능형 데이터로, 강력한 문서 파싱 기술 - 업스테이지 도큐먼트 파스(Document Parse)](https://www.upstage.ai/blog/ko/introduce-upstage-document-parse?page_slug=ko%2Fintroduce-upstage-document-parse)
- [Upstage Docs: Reasoning](https://console.upstage.ai/docs/capabilities/reasoning)