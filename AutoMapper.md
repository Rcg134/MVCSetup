<!-- @format -->

## Package need to install

- AutoMapper.Extensions.Microsoft.DependencyInjection V 11.0.0


## Add configuration in Program.cs

```````bash
builder.Services.AddAutoMapper(typeof(Program).Assembly);

``````````


## Create Class for Mapping Profile
````````

using AutoMapper;
using YourNamespace.Models; structure
using YourNamespace.DTOs;

public class MappingProfile : Profile
{
    public MappingProfile()
    {
        CreateMap<User, UserDTO>();
    }
}

````````


## In your Main Class controller 

### Inject Mapper in constructor

````````
   private readonly IMapper _mapper;
        public HomeController(ILogger<HomeController> logger, BookContext bookContext,IMapper mapper)
        {
            _logger = logger;
            _bookContext = bookContext;
            _mapper = mapper;
        }

````````
