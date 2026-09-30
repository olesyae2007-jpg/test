# test
#include <iostream>
#include <exceptions>

int ** makeMtx(size_t m, size_t n)
{
  int **mtxR = new int * [m];
  try
  {
    for (sie_t i = 0; i < m; ++ i)
    {
      mtxR[i] = new int [n];
    }
  }
  catch (std::bad_alloc() & e)
  {
    rmMtx(mtxR, m);
    throw;
  }

  return mtxR;
}
