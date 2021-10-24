template<std::size_t max = 0, class Head, class ...Types>
constexpr auto max_size_f()
{
    if constexpr(sizeof...(Types) == 0)
    {
        if constexpr(sizeof(Head) > max)
        {
            return sizeof(Head);
        }
        else
        {
            return max;
        }
    }
    else
    {
        if constexpr(sizeof(Head) > max)
        {
            return max_size_f<sizeof(Head), Types...>();
        }
        else
        {
            return max_size_f<max, Types...>();
        }
    }

}

//private
template<class ...Types>
struct max_size
{
    static constexpr std::size_t size = max_size_f<0,Types...>();
};//

template<class ...Types>
inline constexpr std::size_t max_size_v = max_size<Types...>::size;
