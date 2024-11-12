Retrofit使用流程，等待完善

1. 创建网络请求接口对象实例

   Api api = mRetrofit.create(Api.class);

2. 对发送请求进行封装

   Call<Data<Info>> dataCall = api.getJsonData("新歌榜","json")

Post请求

@FormUrlEncoded

@POST("api/comments.163")

call<Object> postDataCall(@Field("format") String format)