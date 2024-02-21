## ndarray의 데이터 타입
- ndarray 내의 데이터값은 숫자 값, 문자열 값, 불 값 등이 모두 가능하다.
- **숫자형의 경우 int형, unsigned int형, float형, 그리고 이보다 더 큰 숫자 값이나 정밀도를 위해 complex 타입도 제공**
- ndarray 내의 데이터 타입은 그 연산의 특성상 같은 데이터 타입만 가능하다. 즉, 한개의 ndarray 객체에 int와 float가 함께 있을 수 없다.
- ndarray 내의 데이터 타입은 dtype 속성으로 확인할 수 있다.
  
```
# 덜적음 p 17
list1 = [1, 2, 3]
print
```
- 리스트 자료형인 list1은 integer 숫자인 1, 2, 3을 값으로 가기고 있으며, 이를 ndarray로 쉽게 변경할 수 있다. 이렇게 변경된 ndarray 내의 데이터 값은 모두 int32형이다.

서로 다른 데이터 타입을 가질 수 있는 리스트와는 다르게 ndarray 내의 데이터 타입은 그 연산의 특성상 같은 데이터 타입만 가능하다고 했는데, 만약 다른 데이터 유형이 섞여 있는 리스트를 ndarray로 변경하면 데이터 크기가 더 큰 데이터 타입으로 형 변환을 일괄 적용한다.

### 다른 데이터 유형이 섞여 있는 리스트 ndarray로 변경
```
In:
# int형과 string형이 섞여 있는 리스트
list2 = [1, 2, 'test']
array2 = np.array(list2)
print(array2, array2.dtype)

# int형과 float형이 섞여 있는 리스트
list3 = [1, 2, 3.0]
array3 = np.array(list3)
print(array3, array3.dtype)

Out:
<class 'numpy,ndarray'>
['1' '2' 'test] <U11
[1. 2. 3.] float64
```
- 숫자형 값 1, 2가 모두 문자열 값인 '1', '2'로 변환되었다.
- 서로 다른 데이터 타입이 섞여 있을 경우 데이터 타입이 더 큰 데이터 타입으로 변환되어 int형이 유니코드 문자열 값으로 변환되었다.
- int형과 float형이 섰여 있는 list3의 경우도 int 1, 2가 모두 1. 2.인 float64형으로 변환되었다.

## astype() 메서드