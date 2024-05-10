#pragma once

namespace SharedPointer {
  template <typename _Ty>
  class SharedPointer {
      _Ty* m_ptr;
      unsigned *m_counter;
  public:
      SharedPointer(_Ty* ptr = nullptr) : m_ptr(ptr), m_counter(new unsigned) {
          *m_counter = 1;
      }
  
      SharedPointer(SharedPointer<_Ty>& s_ptr)
      {
          m_ptr = s_ptr.m_ptr;
          m_counter = s_ptr.m_counter;
          (*m_counter)++;
      }
  
      ~SharedPointer() {
          --(*m_counter);
  
          if (*m_counter == 0) {
              delete m_ptr;
              delete m_counter;
          }
      }
  
      unsigned counter() {
          return *m_counter;
      }
  
      _Ty* get() {
          return m_ptr;
      }
  
      _Ty& operator*() {
          return *m_ptr;
      }
  
      _Ty* operator->() {
          return m_ptr;
      }
  };
}
